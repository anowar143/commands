# Chrome Password Protection on WSL2 (Ubuntu 24)

> **Setup:** Linux Chrome launched from a Windows shortcut via WSLg

---

## How It Works

```
Click Windows shortcut
       ↓
google-chrome-stable (password wrapper)
       ↓
Password prompt in terminal
       ↓
✅ Correct → Chrome opens
❌ Wrong ×3 → Access denied
```

---

## Step 1 — Set Your Linux Password

```bash
passwd
```

Enter and confirm your password. This is what you'll use to unlock Chrome.

---

## Step 2 — Create the Password Wrapper Script

```bash
nano ~/.chrome-lock.sh
```

Paste the following:

```bash
#!/bin/bash
attempts=0
max_attempts=3

while [ $attempts -lt $max_attempts ]; do
    read -s -p "Enter password to open Chrome: " input
    echo

    if printf '%s' "$input" | sudo -S true 2>/dev/null; then
        echo "Access granted. Opening Chrome..."
        /usr/bin/google-chrome-stable.real &
        exit 0
    else
        attempts=$((attempts + 1))
        remaining=$((max_attempts - attempts))
        echo "Wrong password. $remaining attempts remaining."
        sleep 1
    fi
done

echo "Too many failed attempts. Access denied."
exit 1
```

Save: `Ctrl+O` → `Enter` → `Ctrl+X`

---

## Step 3 — Make the Script Executable

```bash
chmod +x ~/.chrome-lock.sh
```

---

## Step 4 — Replace the Chrome Binary with the Wrapper

```bash
# Back up the real Chrome binary
sudo mv /usr/bin/google-chrome-stable /usr/bin/google-chrome-stable.real

# Create the wrapper at the original path
sudo tee /usr/bin/google-chrome-stable > /dev/null << 'EOF'
#!/bin/bash
exec bash ~/.chrome-lock.sh
EOF

# Make it executable
sudo chmod +x /usr/bin/google-chrome-stable
```

---

## Step 5 — Test It

```bash
google-chrome-stable
```

You should see:

```
Enter password to open Chrome:
```

Enter your Linux password → Chrome opens. Done.

> Since your Windows shortcut calls `google-chrome-stable` via WSLg, **no shortcut changes are needed** — the wrapper intercepts automatically.

---

## Useful Commands

| Task | Command |
|------|---------|
| Change password | `passwd` |
| Edit lock script | `nano ~/.chrome-lock.sh` |
| Launch Chrome directly (bypass lock) | `/usr/bin/google-chrome-stable.real` |
