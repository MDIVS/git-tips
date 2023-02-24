# git-tips
Repository created to record Git usage tips that I developed in my daily life

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