## NAME
 git, a minimum viable operating instruction for package git 

## SYNOPSIS

```lang-sh
 # Generic invoation
git [OPTIONS]
```

## DESCRIPTION
A working minimum syntax and minimum flows necessary to make changes to Local and Remote Repositories.


### INSTALLATION

1. [git-scm.com](https://git-scm.com)

### INVOKE

#### Configure user

```lang-sh
git config --global user.name ""
git config --global user.email johndoe@example.com
```
> TIP:  
> `--global` applies for all repos for the current user  
>  `--system` applies for all users in the system  
> `--local` applies for a specific repo  


#### Configure credentials

> TIP: depending on the remote repository, can also use repostiroy authenticator, GitHub for example provides https://github.com/cli/cli

```lang-sh
git config --global credential.helper wincred`

git credential fill
protocol=https
host=github.com
username=<username>
password=<password>
```
#### Working with Local Repostiory

```lang-sh
# create empty local repository
cd <EmptyFolderForRepository>
git init
```

### Working with Remote Repositories

```lang-sh
# download a remote repository
cd {LocalRootFolderOfRemoteSystem}
git clone <url> -b <branchName>
```

#### Full workflow for Remote Repositories
```
 ┌────────────────────────────────────────────────────────────────────────┐
 │  ┌─────────────── ORIGIN REPOSITORY ──┐                                │
 │  │ ************                       │                                │
 │  │ * Branch1  *                       │                                │
 │  │ * ┌─┐  ┌─┐ *                       │                                │
 │  │ * │A├─►│B│ *                       │                                │
 │  │ * └─┘  └┬┘ *                       │                                │
 │  │ ********│***                       │                                │
 │  │         │                          │                                │
 │  │      ***│************************* │                                │
 │  │      *  │   Branch2   ┌─┐        * │                                │
 │  │      *  │             │E├─┐      * │                                │
 │  │      * ┌▼┐  ┌─┐  ┌─┬─►└─┘ │  ┌─┐ * │                                │
 │  │      * │A├─►│C├─►│D│      ├─►│I│ * │           ┌─                   │
 │  │      * └─┘  └─┘  └┬┴─►┌─┐ │  └─┘ * │           │  ┌──────────┐      │
 │  │      *            │   │G├─┘      * │           │  │git commit│    ┐ │
 │  │      *            │   └─┘        * │           │ ┌▼┐     ┌───┴──┐ │ │
 │  │      *************│*************** │           │ │H│     │STAGED│ │ │
 │  │                   │                │           │ └┬┘     └───▲──┘ │ │ 
 │  │                 **│************ ───┘           └──│─STAGING─ │────┘ │
 │  │                 * │Branch3    *                   │          │      │
 │  │                 *┌▼┐  ┌─┐  ┌┐ *           git push│          │      │
 │  │                 *│D├─►│F│  │◄─────────────────────┘          │      │
 │  │                 *└─┘  └┬┘  └┘ *      ┌ WORKING TREE ┐        │      │
 │  └─────────────────*******│*******      │  FolderA     │        │      │
 │                           │             │  ├file1      │        │      │
 │                           │git clone    │  └FolderB    │git add │      │
 │                           └─────────────┤   └file3     ├────────┘      │
 │                                         └   └file4     ┘               │
 └────────────────────────────────────────────────────────────────────────┘
```
#### Fundamentals of making changes 
```lang-sh
# choose branch to show in the Work Tree (file system)
git switch origin <branchName>
```
```lang-sh
# download latest changes from ORIGIN
git pull --all
```
```lang-sh
# create commit
git commit -a -m <commit message text>
```
```lang-sh
# check status for any missed changes
git status
```
```lang-sh
# Send commit snapshots to remote repository
git push origin
```

### EXPLANATORY NOTES

#### Moving files

> TIP: using git mv when rename, moving files keeps association to the file history. Using Filesystem delete or rename will detach history from current file. 

#### Structure of locally cloned Repository 

```
  └─`ORIGIN` the *Remote Repository*, perminent location where data is version controled and stored).
      ├─`WORK TREE` the user makes changes in this tree, it is a local copy of a remote repostiroy visible as file system files and folders.
      └─`GIT DIR` the *Staging* folder, by default `.git` subdirectory.
          ├─`GIT INDEX FILE` the list of working Tree changes that will be committed at the next `git commit`
          └─`GIT OBJECT DIRECTORY` the *local repository* or *staging*, hidden from the user, all changes that are version controlled (for instance `git commit` or `git pull`).
```
 
#### Commands Local Repository commands

```
 ┌─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┐
 │   ┌─────────────────────────────────────────────────────┐                                                                   │
 │   │                 Local File System                   │                                                                   │
 │   └─┬───────────────┬───────┬──────────────────────┬────┘        ┌────────┐                                                 │
 │     │   Work Tree   │       │    GIT REPOSITORY    │             │ Remote │                                                 │
 │     └───────┬───────┘       └───────────────────┬──┘             └───┬────┘                                                 │
 │             │                                   │                    │    REPOSITORY LIFECYCLE                              │
 │             │                                   │                    │                                                      │
 │             │                                   │           git clone│    1. create the local repository                    │
 │             │◄──────────────────────────────────┤◄───────────────────┤                                                      │
 │      del *  │                                   │                    │    3. delete the local repository                    │
 │     ───────►├──────────────────────────────────►│                    │                                                      │
 └─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┘
 ┌─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┐
 │   ┌─────────────────────────────────────────────────────┐                                                                   │
 │   │                 Local File System                   │                                                                   │
 │   └─┬───────────────┬───────┬──────────────────────┬────┘        ┌────────┐                                                 │
 │     │   Work Tree   │       │    GIT REPOSITORY    │             │ Remote │                                                 │
 │     └───────┬───────┘       └───────────────────┬──┘             └───┬────┘                                                 │
 │             │                                   │                    │    FUNDAMENTAL VERSION CONTROL                       │
 │             │                                   │                    │                                                      │
 │             │                                   │            git pull│    1. git pull                                       │
 │             │◄──────────────────────────────────┤◄───────────────────┤         fetch latest remote repository commits       │
 │             │                                   │                    │                                                      │
 │             │ git commit -a -m                  │                    │    2. git commit -a -m <message>                     │
 │             ├──────────────────────────────────►│                    │         commits all working directory changes.       │
 │             │                                   │                    │         simple process does not stage files.         │
 │             │            git status             │                    │    3. git status                                     │
 │             │◄─────────────────────────────────►│                    │         list status of each file                     │
 │             │                                   │                    │         (unstanged > staged > committed)             │
 │             │                                   │ git push           │    4. git push origin                                │
 │             │                                   ├───────────────────►│         write commits to Remote repository           │
 └─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┘
 ┌─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┐
 │   ┌─────────────────────────────────────────────────────┐                                                                   │
 │   │                 Local File System                   │                                                                   │
 │   └─────────┬───────────────┬────────────────────┬──────┘                                                                   │
 │             │               │     GIT FOLDER     │                                                                          │
 │             │               └────┬──────────┬────┘                                                                          │
 │             │                    │          │                                                                               │
 │     ┌───────┴───────┐     ┌──────┴─┐      ┌─┴─────────┐          ┌────────┐                                                 │
 │     │   Work Tree   │     │ Staged │      │ Committed │          │ Remote │                                                 │
 │     └───────┬───────┘     └────┬───┘      └─────┬─────┘          └───┬────┘                                                 │
 │             │                  │                │                    │    VERSION CONTROL                                   │
 │             │ git add          │                │                    │                                                      │
 │             │ git add -A       │                │                    │    1. git add -A                                     │
 │             │ git rm (remove)  │                │                    │         stage working tree changes in local repo     │
 │             │ git mv (move)    │                │                    │    2. git mv <source> <desitnation>                  │
 │             ├─────────────────►│                │                    │         move and rename files,                       │
 │             │                  │                │                    │         keep version history with new file.          │
 │             │ git reset        │                │                    │                                                      │
 │             │ git restore      │                │                    │    3. git restore                                    │
 │             │◄─────────────────┤                │                    │        remove staging index, changes 'unstaged'      │
 │             │                  │                │                    │        does not alter the work tree files            │
 │             │                  │ git commit -m  │                    │    4. git commit -m <message text>                   │
 │             │                  ├───────────────►│                    │         create snapshot ready for remote repository  │
 │             │                  │                │                    │         NOTE: --ammend will append to current commit │
 │             │ git stash push   │                │                    │    5. git stash push -m <message>                    │
 │             │◄────────────────►│                │                    │         staged changes stored locally with message   │
 │             │◄────────────────►│                │                    │         staged changes stored locally with message   │
 │             │ git stash list   │                │                    │    6. git stash list                                 │
 │             │      ───────────►│                │                    │         list of all stashed changes                  │
 │             │ git stash apply  │                │                    │    7. git stash apply <stashName                     │
 │             │◄─────────────────┤                │                    │         remove all changes from working tree         │
 │             │                  │                │                    │         restore named stash                          │
 │             │                                   │    git fetch       │    8. git fetch <remote>                             │
 │             │                                   ├───────────────────►│         downloads all data from remote repository    │
 │             │                                   │                    │                                                      │
 │             │                        git switch │                    │    9. git switch origin <branch>                     │
 │             │◄──────────────────────────────────┤                    │         upate work tree files to another branch      │
 │             │                                   │                    │                                                      │
 │             │                        git rebase │                    │                                                      │
 │             │                         git merge │                    │   10. git merge <branch>                             │
 │             │                       ┌───────────┤                    │         add changes from another branch to work tree │
 │             │◄──────────────────────┤           │                    │                                                      │
 │             │                       └───────────┤                    │                                                      │
 │             │                                   │                    │                                                      │
 │             │                  git bisect start │                    │                                                      │
 │             │                    git bisect bad │                    │                                                      │
 │             │                   git bisect good │                    │  11. git bisect                                      │
 │             │                       ┌───────────┤                    │         semi automated fetch of specific versions    │
 │             │◄──────────────────────┤           │                    │         Assist in identifying version with bug.      │
 │             │                       └───────────┤                    │                                                      │
 └─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┘
```

#### Fetch and Pull
1. `git fetch` downloads the latest updates from the remote repository into the local repository
2. `git pull` runs `git fetch` then attempts to reconcile remote changes to the working tree using `git rebase` or `git merge`

#### Merge and Rebase
1. `git merge` when a user commits to a branch two different commits are made to the same branch, 


snapshot
branch

working tree
staging area (Staged)
git directory (Committed)
remote repository

remote 
untracked
staged
committed



## DEPENDENCIES

PACKAGE == VERSION

## REFERENCES

  [1]: # ️TODO

