# 🔹 Tutorial: Fix Bangla (Bengali) Font Rendering in Ubuntu / WSL

This guide will help you fix **Bangla (Bengali) text rendering issues** in **Ubuntu or WSL (Windows Subsystem for Linux)**.  

Sometimes Bengali text appears as:

- ☐☐☐ boxes  
- broken characters  
- incorrect **kar / fola placement**

This happens when the system **does not have proper Bengali fonts installed**.

---

# 1️⃣ Update and Install Bangla Fonts

The most common reason for **broken Bangla text** is the lack of a proper **rendering engine and fonts**.

Run the following commands:

```bash
sudo apt update
sudo apt install fonts-beng fonts-beng-extra fonts-noto-core
```

These packages install the **standard Bengali fonts** used in Linux.

---

# 2️⃣ (Optional) Install Google Noto Fonts

Google's **Noto Sans Bengali** is highly recommended for **web browsing and modern applications**.

It handles **complex Bengali scripts (like juktakkhor)** much better than older fonts.

Install it using:

```bash
sudo apt install fonts-noto-ui-core fonts-noto-bengali
```

This provides better support for:

- Bengali ligatures
- modern web rendering
- UI compatibility

---

# 3️⃣ Clear Font Cache

After installing new fonts, the system needs to **refresh its font cache** so applications can detect them.

Run:

```bash
sudo fc-cache -f -v
```

This will:

- rebuild the font cache
- allow browsers and apps to detect the new fonts

---

# 4️⃣ Browser Specific Fix (Firefox)

If the fonts are installed but still appear **misaligned or broken** in Firefox (for example **kar / fola in wrong positions**), you may need to manually configure the font.

### Step 1

Open **Firefox Settings**

### Step 2

Search for:

```
Fonts
```

Then click:

```
Advanced...
```

### Step 3

In the **Fonts for** dropdown select:

```
Bengali
```

### Step 4

Set the fonts to:

```
Serif: Noto Sans Bengali
Sans-serif: Noto Sans Bengali
```

or

```
Lohit Bengali
```

### Step 5

Restart Firefox.

---

# 5️⃣ Troubleshooting Windows-Side Fonts (WSL)

If you are using **WSL2**, sometimes the issue is related to **Windows font rendering** instead of Ubuntu.

Because **WSLg shares the display system with Windows**, fonts may not load correctly.

---

## Restart WSL

Open **PowerShell on Windows** and run:

```powershell
wsl --shutdown
```

Then reopen your **Ubuntu terminal**.

---

## Chrome / Edge Users

If you are using **Chrome or Edge installed on Windows** to access a **WSL-hosted website**, make sure Windows has proper Bengali fonts installed.

Recommended Windows fonts:

- **Nirmala UI** (default Windows Bengali font)
- **Kalpurush**

These fonts ensure proper **Bangla rendering in Windows browsers**.

---

# ✅ Success!

Your system should now correctly display **Bangla text** in:

- Ubuntu
- WSL
- Firefox
- Chrome
- Edge

without broken characters or missing glyphs.

---

# 📌 Quick Command Summary

```bash
sudo apt update
sudo apt install fonts-beng fonts-beng-extra fonts-noto-core
sudo apt install fonts-noto-ui-core fonts-noto-bengali
sudo fc-cache -f -v
```

Restart WSL if necessary:

```powershell
wsl --shutdown
```
