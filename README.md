# git-tips
Repository created to record Git usage tips that I developed in my daily life

# Rename branch
Renaming a local branch
```
git checkout <old-branch-name>
git branch -m <new-branch-name>
```

Renaming a remote branch  
To rename a remote branch you will need to delete the actual branch and repblish the entire branch with the new name.

# How to untrack file or folder after added into .gitignore file
Sometimes I just want to remove a file or folder only from the git repository after have been added it to the git stage. Is those cases I usually follow these steps:

1. Create .gitignore file in repository root:
```
path_to_folder/to_ignore
path_to_file/to_certanly_ignore.txt
```

2. Remove all files and folders from the git stage
```
git rm -r --cached ./path_to_folder/to_ignore
git rm --cached ./path_to_folder/to_certanly_ignore.txt
```

# Merge commit from branchA to branchB
```
$ git checkout branchA
$ git rev-parse HEAD
  <commit>
$ git checkout branchB
$ git cherry-pick <commit>
```

# Add a GitHub SSH Key on Windows
A technical resume of [this article](https://syntaxbytetutorials.com/add-a-github-ssh-key-on-windows/).

```
$ ssh-keygen -t rsa -b 4096 -C "example@example.com"
```

```
$ eval $(ssh-agent -s)
```

```
$ ssh-add ~/.ssh/id_rsa
```

```
$ clip < ~/.ssh/id_rsa.pub
```