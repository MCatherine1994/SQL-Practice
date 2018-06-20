### **Create a new branch**  
```
$ git branch       //list the current branch
$ git branch new_branch_name      //create a branch with the new branch name
```
### **Switch between branch**  
```
$ git checkout branch_name
```  
### **Save new changes and push up**  
```
$ git status     //check the modified files, should be in red color
$ git add .      //add all or $ git add <Filename> add a single file
$ git status     //now the filename becomes green
$ git commit -m "any comment"
$ git log       //see if all the changes have been made or $ git log -p to see the full version of the changes
$ git push origin branch_name      //add the branch to the origin repository
$ git pull origin branch_name      //if want to get the new version, pull from the origin repository
```  
