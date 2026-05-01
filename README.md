 # Goal ?
 this repo contains the solutions for exercises from https://gitexercises.fracz.com 
 this is my attempt for solving these questions, so feel to try your own or share a better solution with me. 

**follow the instructions on the main website to prepare the lab and start practicing from terminal**

---

# Solutions:

---

## 1: master 
*this exercise is just to verify everything is working the right way*

```
$> git start 
$> git verify 
```
*you can use git push instead of git verify, but verify is less noisy*

---

## 2: commit-one-file 

---

## 8: change-branch-history
*rebase is the keyword here*
```
$> git branch change-branch-history
$> git rebase hot-bugfix
$> git verify 
```

---

## 9: remove-ignored 
```
$> git rm --cached ignored.txt
$> git commit -m "removed ignored.txt file"
$> git verify 

*git rm --cached : stop tracking this file, but leave it alone locally*
*git rm : alone it will delete the file everywhere*
```

---

## 10: case-sensitive-filename
```
$> git reset HEAD^   
$> mv File.txt file.txt 
$> git add  file.txt 
$> git commit -m "changed filename to lowercase"
$> git verify 
```
*git reset HEAD^ --> moves your branch one commit backward and updates working tree.*

---

## 11: fix-typo 
```
$> vi file.txt # edit the text inside the file to hello world
$> git commit -a --amend  # edit the commit message to be hello world 
$> git verify 

```

---

## 12: forge-date 
```
$> git commit --amend --no-edit --date="1987-04-01"
```
*just editing the date without editing commit message or anything*

---

## 13: fix-old-typo 
```
$> git rebase -i HEAD~2
*replace pick with "edit" with the line that has "Add Hello wordl"*
$> vi file.txt   # and then fix the typo in the file
$> git add file.txt 
$> git commit --amend  # fix the typo in the commit message 
$> git rebase continue 

```
