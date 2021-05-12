# First Commit

```
git init
git add .
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
git commit -m "first commit"
git remote add origin https://github.com/anowar143/django-food.git
git remote -v
git branch -M main
git push -u origin main
Username for 'https://github.com':      ""you@example.com""
Password for 'https://"you@example.com"@github.com':  "Password"
```


# git push

```
git add 'file name' or 'add .'
git commit -m "change commit"   #if u want change commit
git git push -u origin master/main
```

# git pull

```
git add 'file name' or 'add .'
git commit -m "preview commit"
git pull origin master/main
git push -u origin master/main
```


# Commands

```
git init              #it will create a new git repository.


git add [filename]    #will add a specific file to the Staging Area from your Working Tree:    

git add .             #Stages new and modified files, without deleting.

git add -a            #Stages all files.

git add -u            #Stages modified and deleted, without new.

git status            # This command will show you two things: The files in your Working Tree and the files in your Staging Area.

git checkout file-name           #To revert the changes of a modified file.

git rm --cached file-name        #To remove the file from the staging area the command is:

git commit -m "first commit"     #Taking all the changes in the Staging Area.

git commit            #The git commit command captures a snapshot of the projects currently staged changes.

git commit -a         #Commit a snapshot of all changes in the working directory.

git commit -m “commit message”   #A shortcut command that immediately creates a commit with a passed commit message


git commit -am “commit message”  #A power user shortcut command that combines the -a and -m options. This combination immediately creates a commit of all the staged changes and takes an inline commit message.


git remote add origin <repository url>

git push -u origin master

git reset --hard HEAD^           # command it will only revert the top commit means the latest commit.

git reset --soft HEAD^           # --soft option means it will reset the commit but don’t reset the content in that commit file.
```



