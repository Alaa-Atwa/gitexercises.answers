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
$> git verify
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
$> git verify

```
---

## 14: commit-lost 
```
*you need to find where was the previous head using reflog then reset to it*
$> git reflog 
$> git reset --hard HEAD@{2}
$> git verify  

```

---

## 15: split-commit 
```
$> git reset HEAD^  
$> git add first.txt 
$> git commit -m "added first file"
$> git add second.txt 
$> git commit -m "added second file"
$> git verify

```
---

## 16: too-many-commits
```
$> git rebase --interactive   
*change "pick" from the second commit that sasy "oh, crap.." to be "squash"*
$> git verify 
```
---

## 17: executable
```
$> git reset HEAD^
$> git add script.sh --chmod=+x 
$> git commit -m "adding the executable script.sh file"
$> git verify 

```
*you can use git update-index instead* 
---
## 18: commit-parts
*using patching option when adding the file, then s to shunk and typing y for wanted parts and n for not wanted parts* 
```
$> git add -p file.txt* 
- type s 
- type y for wanted parts in the first commit (parts has task 1 in it)
- type n for unwanted parts for the first commit 
$> git commit -m "task 1 parts"
$> git commit -am "task 2 parts"
$> git verify
    
```
---
## 19: pick-your-feature 
```
$> git cherry-pick feature-a
$> git cherry-pick feature-b
$> git merge feature-c 
# solve the conflict by opening the file and removing lines that contain ====== or <<<<< 
$> git add program.txt 
$> git commit -m "finished picking features"
$> git verify

# or in one line 

$> git cherry-pick feature-a feature-b feature-c 
# solve the confilct as previous 
$> git add program.txt 
$> git commit -m "finished picking features"
$> git verify

```
---
## 20: rebase-complex 
*using --onto will solve this exercise easily*
```
$> git rebase --onto your-master issue-555 rebase-complex 
$> git verify

```
---
## 21: invalid-order 
```
$> git rebase --interactive 
# switch the order of commits (commits start with pick keyword)
# save 
$> git verify
```
---
## 22: find-swearwords
```
```
---

















































