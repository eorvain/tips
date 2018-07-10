# tips Git

## Git multiple accounts :
```
git config --global credential.https://github.com/elmanu2/sandbox.git.username elmanu2
Git config --local user.name elmanu2
Git config -- local user.email eorvain@gmail.com
Faire git push depuis bash.
```

## Portable git on windows :
https://code.google.com/p/msysgit/downloads/list

## Create git repository :
#### On local machine
```
cd foo_project
git init
git add *
git commit -m "My initial commit message"
```

## Clone git repository (git clone can only be done in an empty folder) 
```
git clone url:port/repository_path .
```

## Clone git repository in a non empty folder
```
git clone url:port/repository_path temp_folder
cp -R temp_folder/ working_directory/
cp -R temp_folder/.git working_directory/
```

## List of local branches
```
git branch
```
## List of local and remote branches
```
git branch -a
```
## List of remote branches
```
git branch -r
```

## Switch working directory to a branch :
```
git checkout branch_name
```

## Create a new local and switch working directory on it :
```
git checkout -b my_branch
```

## To push that branch to the repository :
```
git push origin my_branch
```

## Create new branch and push to repository :
```
bname=your_branch_name
git checkout -b $bname
git push origin $bname
git checkout master
git branch -d $bname
git checkout $bname
```

## Branch merging (force to make a commit)
```
git checkout master
git merge --no-ff iss53
git push
```

## Delete a local branch
```
git branch -d the_local_branch
```

## Remove remote branch (if you know what you are doing!)
```
git push origin :the_remote_branch
```

## Merge(checkout) specific files from specific branch
```
git checkout main (we are on main branch)
git checkout distantbranch *.c *.h
```
(merge files from another directory)
```
cd source/
git checkout distantbranch *.c *.h
...
``
