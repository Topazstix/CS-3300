# Documentation of How To
## Contents
- [Usefull Commands](#Usefull-Commands)
- [Push Help](#Pushing)
  - [Push Permision Error](#Permission-Error)
  - [Push Rejected Error](#Rejected-Error)
- [Tagging](#Tagging)

## Usefull Commands

`cd` Change directory 

`git status` gives you a summary of what you have edited

`git log` shows you a summary of all the commits that have been done

`git branch` shows a list of all branches including which one your in

`git branch name` creates a branch with that name\

`ls` shows the files in current directory
  
## Pushing
Once you have edited all the files you want go ahead and do this.
```
git add .
git commit -m <commit message>
git push --set-upstream origin
```
### Permission Error
if you recive a message that looks like this:
```
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.
```
then try 
```
chmod 600 /your/key/location/on/computer
```
### Rejected Error
if you recive a message that looks like this:
```
 ! [rejected]        PracticeMerging -> PracticeMerging (fetch first)
error: failed to push some refs to 'github.com:Awsome-O-clocks/CS-3300.git'
hint: Updates were rejected because the remote contains work that you do not
hint: have locally. This is usually caused by another repository pushing to
hint: the same ref. If you want to integrate the remote changes, use
hint: 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```
then your push is conflicting with your current version try:
```
git pull origin
```
Now you can run your push command

## Tagging

When your ready to tag a version heres how. First your going to want to find the commit ID run
```
git log  --pretty=oneline
```
This will show you all the commits you've done look for the one that has the message you are looking for and note the first 5 or so characters of 
the Commit ID.
Next run the commands
```
git tag -a <label your tag> -m <add a description here> <commit ID>
git push origin --tags
```
If you want to check the tags curently saved run
```
git tag
```




