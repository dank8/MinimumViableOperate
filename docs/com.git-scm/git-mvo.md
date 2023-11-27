## NAME
 git, a minimum viable operating instruction for package git 

## SYNOPSIS

```lang-sh
 # Generic invoation
git [OPTIONS]
```

## DESCRIPTION
A working examples of minimum syntax and minimum flows necessary to sync with a Remote project.

> QUOTE FROM DEVELOPER

### INSTALLATION

1. [git-scm.com](https://git-scm.com)

### INVOKE

- `--global` applies for all repos for the current user
- `--system` applies for all users in the system
- `--local` applies for a specific repo

#### Configure user

> depending on the remote repository, may prefer to use that repositories authentication method, for example https://github.com/cli/cli

```lang-sh
git config --global user.name ""
git config --global user.email johndoe@example.com
```

#### Configure credentials

```lang-sh
git config --global credential.helper wincred`

git credential fill
protocol=https
host=github.com
username={username}
password={password}
```

#### Create repository

```lang-sh
# start with local repository
cd {RootfolderOfRepository}
git init
```

```lang-sh
# fetch a remote repository
cd {LocalRootFolderOfRemoteSystem}
git clone {url}
```

### Work process

#### Modfy the Staging area

1. copy all branches to staging area
```lang-sh
git fetch --all
```
1. choose branch to show in the FileSystem
```lang-sh
git switch origin <branchName>
```
1. copy latest remote repo to local staging
```lang-sh

```
1. Make changes from the file system. 
1. Update file changes into staging area:
```lang-sh
git add -A
```
> TIP: using `git mv` when rename, moving files keeps association to the file history. Using Filesystem delete or rename will detach history from current file. 
1. Move files 
```lang-sh
1. Check delta's between file system and staging area. 
```lang-sh
git status
```
# move file or rename file
git mv \path\folder\file.txt \path\newFolder\newFile.txt
#rename file
git mv .\file.txt .\newFile.txt
```
3. Commit changes to the Staging area
Commit changes:
```lang-sh
git commit -m "Your commit message"
```
1. Send staging area the remote repository
```lang-sh
git push origin
```
1. others:


Merge branches:
```lang-sh
git merge <branch_name>
```
Pull changes from a remote repository:
```lang-sh
git pull origin <branch_name>
```
Push changes to a remote repository:
```lang-sh
git push origin <branch_name>
```
See the changes between two commits:
```lang-sh
git diff <commit1> <commit2>
```

### EXPLANATORY NOTES

1. # ️TODO

## DEPENDENCIES

PACKAGE == VERSION

## REFERENCES

  [1]: # ️TODO

