## **Git Command**
**Branch**  
```
$ git branch       //list the current branch
$ git branch new_branch_name      //create a branch with the new branch name
$ git fetch  // get both the remote and local repository
$ git remote show <remote_name>   // show remote repository branches

$ git branch -d branch_name   // delete local branch
$ git branch -D branch_name   // force delete local branch
$ git push --delete origin branch_name    // delete remote branch, but won't delete the local one
```
**Switch between branch**  
```
$ git checkout branch_name    // to local branch
$ git checkout --track origin/newsletter   // to remote branch newsletter, and a local branch newsletter will be created
```  
**Save new changes and push up related commits**  
```
$ git status     //check the modified files, should be in red color
$ git add .      //add all or $ git add <Filename> add a single file
$ git status     //now the filename becomes green
$ git diff       //see the eact different code 
$ git checkout -- filename   // revert changes back to origin
$ git reset filename    // undo git add
$ git commit -m "any comment"
$ git log       //see if all the changes have been made or $ git log -p to see the full version of the changes
$ git push origin branch_name      //add the branch to the origin repository
$ git pull origin branch_name      //if want to get the new version, pull from the origin repository
```  
**Remote repository**  
```
$ git remote -v   // check remote repository
$ git remote add repo_name repo_address    // add a new remote repository, repo_address could be url or hard drive (hard drive ends by .git)
$ git remote rm repo_name
```
**Tags**  
```
$ git tag   // show tags
$ git push --tag <remote_name>   // push tags to remote repository
```  
**Compare the same file in two different branch**  
```
$ git diff branchA branchB -- file.cs
``` 
**[Remove Sensitive data files from git commit history](https://help.github.com/en/articles/removing-sensitive-data-from-a-repository#using-filter-branch)**   
ref reading:   
[git filter-branch](https://git-scm.com/docs/git-filter-branch)  
[git rm](https://git-scm.com/docs/git-rm)  
```
git filter-branch --force --index-filter "git rm -r --cached --ignore-unmatch path/to/file(or path/to/folder/)" --prune-empty --tag-name-filter cat -- --all
```

**Remove Git history**
```
# in Linux, simply remove the .git folder
$ ls -al   # list all file in the current folder
$ rm -rf .git
$ git init .  # will create a new empty git repository
```

