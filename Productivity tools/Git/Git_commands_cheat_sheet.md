# Git cheat sheet

## Setup a git repository
- To initialize the repository : `git init`
- Here you sould create a *.gitignore* file at your project's root to add the file you don't want to track
- To add all the files in the foldr : `git add .` if you want to remove some files `git rm <filename>`
- To commit : `git commit -m "message"`
- To push to local repository : `git push <your_remote_name>`
### With remote repository
- To add a remote repository `git remote add origin <remote_url>` *to do once at the beginning of the project*
- To verify remote url : `git remote -v`
- To push to a remote repository `git push origin`


## Clone
- To clone remote repository : `git clone <remote_url>`
- To clone specific branch of the remote repository : `git clone -b <branch_name> <remote_url>`

## Pull Fetch Push
- To push local commit to repository : `git push` if there is a remote repository `git push origine`
- To integrate the remote modifications : `git pull origin`

## Branch
- To create branche : `git checkout -b <branch_name>`
- To list all branches : `git branch -a`
- To change branche : `git checkout --track <remote_name>/<branch_name>`
- To remove local branch : `git branch -d <local_branch_name>`
- To remove remote branch : `git push origin --delete <remote_branch_name>`

## Usefull links-
- [magic tricks](https://ohshitgit.com/)



