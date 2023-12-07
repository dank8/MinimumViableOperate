## NAME
 git, a minimum viable operating instruction for package git 

## SYNOPSIS

```lang-sh
<<<<<<< HEAD
 # Generic invocation
git -h
```

## DESCRIPTION
List of minimum commands needed to stage file changes to a version control system with a minimum workflow.


## INSTALLATION

1. [git-scm.com](https://git-scm.com)

## INVOKE

### Configure user

```lang-sh
git config --global user.name "John Doe"
git config --global user.email "johndoe@example.com"
```
> TIP:    
> `--global` apply configuration to current user  
>  `--system` apply configuration to all all users in the system    
> `--local` apply the configuration for the current repository  


### Configure credentials

```lang-sh
git config --global credential.helper wincred
=======
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
>>>>>>> origin/main

git credential fill
protocol=https
host=github.com
username=<username>
password=<password>
```
<<<<<<< HEAD

> TIP: some repository hosting services provide an authenticator that integrates with git, for example GitHub https://github.com/cli/cli

### Working with Local Repository

```lang-sh
cd <EmptyFolderForRepository>
# Create an empty local repository
git init
```

## Working with Remote Repositories

```lang-sh
cd {LocalRootFolderOfRemoteSystem}
# download a remote repository
git clone <url> -b <branchName>
```

### Modification Workflow of GIT Repositories
=======
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
>>>>>>> origin/main
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
<<<<<<< HEAD
### Fundamentals of making changes 

```lang-sh
# choose the branch you want to edit in the Work Tree (file system)
git switch origin <branchName>
```

```lang-sh
# download the latest changes from ORIGIN
git pull --all
```

=======
#### Fundamentals of making changes 
```lang-sh
# choose branch to show in the Work Tree (file system)
git switch origin <branchName>
```
```lang-sh
# download latest changes from ORIGIN
git pull --all
```
>>>>>>> origin/main
```lang-sh
# create commit
git commit -a -m <commit message text>
```
<<<<<<< HEAD

```lang-sh
# check the status for any missed changes
git status
```

```lang-sh
# Send commit snapshots to the remote repository
git push origin
```

## EXPLANATORY NOTES

### Moving files

> TIP: use `git mv` instead of File System `mv`, `rename`. `git` is aware of the commit history (the file system is not). `git` changes the file name or path and at the same time, it maintains the association between the new file and the previous file commit history.

### Structure of locally cloned Repository 

```
  └─`ORIGIN` the *Remote Repository*, permanent location where data is version controlled and stored).
      ├─`WORK TREE`, the user makes changes in this Tree. It is a local copy of a remote repository visible as file system files and folders.
      └─`GIT DIR` the *Staging* folder, by default `.git` subdirectory.
          ├─`GIT INDEX FILE` the list of staged Working Tree changes when doing `git commit`
          └─`GIT OBJECT DIRECTORY` the *local repository* or *staging*, hidden from the user, all changes that are version controlled (for instance `git commit` or `git pull`).
```
 
### Commands Local Repository commands
=======
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
>>>>>>> origin/main

```
 ┌─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┐
 │   ┌─────────────────────────────────────────────────────┐                                                                   │
 │   │                 Local File System                   │                                                                   │
 │   └─┬───────────────┬───────┬──────────────────────┬────┘        ┌────────┐                                                 │
 │     │   Work Tree   │       │    GIT REPOSITORY    │             │ Remote │                                                 │
 │     └───────┬───────┘       └───────────────────┬──┘             └───┬────┘                                                 │
 │             │                                   │                    │    REPOSITORY LIFECYCLE                              │
 │             │                                   │                    │                                                      │
<<<<<<< HEAD
 │             │                                   │           git clone│    1. Create the local repository                    │
=======
 │             │                                   │           git clone│    1. create the local repository                    │
>>>>>>> origin/main
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
<<<<<<< HEAD
 │             │◄──────────────────────────────────┤◄───────────────────┤         Fetch the latest remote repository commits   │
=======
 │             │◄──────────────────────────────────┤◄───────────────────┤         fetch latest remote repository commits       │
>>>>>>> origin/main
 │             │                                   │                    │                                                      │
 │             │ git commit -a -m                  │                    │    2. git commit -a -m <message>                     │
 │             ├──────────────────────────────────►│                    │         commits all working directory changes.       │
 │             │                                   │                    │         simple process does not stage files.         │
 │             │            git status             │                    │    3. git status                                     │
 │             │◄─────────────────────────────────►│                    │         list status of each file                     │
<<<<<<< HEAD
 │             │                                   │                    │         (unstaged > staged > committed)              │
=======
 │             │                                   │                    │         (unstanged > staged > committed)             │
>>>>>>> origin/main
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
<<<<<<< HEAD
 │             │                  │                │                    │         keep version history with the new file.      │
 │             │ git reset        │                │                    │                                                      │
 │             │ git restore      │                │                    │    3. git restore                                    │
 │             │◄─────────────────┤                │                    │        Remove staging index, changes 'unstaged'      │
 │             │                  │                │                    │        does not alter the work tree files            │
 │             │                  │ git commit -m  │                    │    4. git commit -m <message text>                   │
 │             │                  ├───────────────►│                    │         create snapshot ready for remote repository  │
 │             │                  │                │                    │         NOTE: --ammend will append to previous commit│
=======
 │             │                  │                │                    │         keep version history with new file.          │
 │             │ git reset        │                │                    │                                                      │
 │             │ git restore      │                │                    │    3. git restore                                    │
 │             │◄─────────────────┤                │                    │        remove staging index, changes 'unstaged'      │
 │             │                  │                │                    │        does not alter the work tree files            │
 │             │                  │ git commit -m  │                    │    4. git commit -m <message text>                   │
 │             │                  ├───────────────►│                    │         create snapshot ready for remote repository  │
 │             │                  │                │                    │         NOTE: --ammend will append to current commit │
>>>>>>> origin/main
 │             │ git stash push   │                │                    │    5. git stash push -m <message>                    │
 │             │◄────────────────►│                │                    │         staged changes stored locally with message   │
 │             │◄────────────────►│                │                    │         staged changes stored locally with message   │
 │             │ git stash list   │                │                    │    6. git stash list                                 │
 │             │      ───────────►│                │                    │         list of all stashed changes                  │
 │             │ git stash apply  │                │                    │    7. git stash apply <stashName                     │
<<<<<<< HEAD
 │             │◄─────────────────┤                │                    │         remove all changes from working Tree         │
=======
 │             │◄─────────────────┤                │                    │         remove all changes from working tree         │
>>>>>>> origin/main
 │             │                  │                │                    │         restore named stash                          │
 │             │                                   │    git fetch       │    8. git fetch <remote>                             │
 │             │                                   ├───────────────────►│         downloads all data from remote repository    │
 │             │                                   │                    │                                                      │
 │             │                        git switch │                    │    9. git switch origin <branch>                     │
<<<<<<< HEAD
 │             │◄──────────────────────────────────┤                    │         update work tree files to another branch     │
 │             │                                   │                    │                                                      │
 │             │                        git rebase │                    │                                                      │
 │             │                         git merge │                    │   10. git merge <branch>                             │
 │             │                       ┌───────────┤                    │         add changes from another branch to work Tree │
=======
 │             │◄──────────────────────────────────┤                    │         upate work tree files to another branch      │
 │             │                                   │                    │                                                      │
 │             │                        git rebase │                    │                                                      │
 │             │                         git merge │                    │   10. git merge <branch>                             │
 │             │                       ┌───────────┤                    │         add changes from another branch to work tree │
>>>>>>> origin/main
 │             │◄──────────────────────┤           │                    │                                                      │
 │             │                       └───────────┤                    │                                                      │
 │             │                                   │                    │                                                      │
 │             │                  git bisect start │                    │                                                      │
 │             │                    git bisect bad │                    │                                                      │
 │             │                   git bisect good │                    │  11. git bisect                                      │
<<<<<<< HEAD
 │             │                       ┌───────────┤                    │         semi-automated fetch of specific versions    │
=======
 │             │                       ┌───────────┤                    │         semi automated fetch of specific versions    │
>>>>>>> origin/main
 │             │◄──────────────────────┤           │                    │         Assist in identifying version with bug.      │
 │             │                       └───────────┤                    │                                                      │
 └─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┘
```

<<<<<<< HEAD
### Fetch and Pull

- `git fetch` downloads the latest updates from the remote repository into the local repository
- `git pull` runs `git fetch` then attempts to reconcile remote changes to the working tree using `git rebase` or `git merge`

### Merge and Rebase

Both commands resolve a conflict where there is more than one 'latest' commit on the branch. Conflicts are resolved by merging all 'latest' commits into a single new commit snapshot. The two commands work differently with how they modify the history.

```
 ┌─────────────────────────────┐
 │ Branch2                     │
 │ ┌─┐  ┌─┐  ┌─┐               │
 │ │A├──┤B├──┤D│               │
 │ └─┘  └┬┘  └─┘               │
 │       │   ┌─┐               │
 │       └───┤C│               │
 │           └─┘               │
 └─────────────────────────────┘
```

`git merge` does not alter the branch snapshot history. It combines all changes into a single 'latest' commit snapshot.

```
 ┌─────────────────────────────┐
 │ Branch2                     │
 │ ┌─┐  ┌─┐  ┌─┐               │
 │ │A├──┤B├──┤D├─┐             │
 │ └─┘  └┬┘  └─┘ │git merge┌─┐ │
 │       │   ┌─┐ ├────────►│E│ │
 │       └───┤C├─┘         └─┘ │
 │           └─┘               │
 └─────────────────────────────┘
```

`git rebase` alters the history, removing all but one of the conflicting commit snapshots. All changes are combined to form a single 'latest' commit snapshot. Many developers prefer the `rebase` method as it simplifies the history and its comprehension.

```
 ┌─────────────────────────────┐
 │ Branch2                     │
 │ ┌─┐  ┌─┐  ┌─┐git rebase┌─┐  │
 │ │A├─►│B├─►│D├─────────►│E│  │
 │ └─┘  └─┘  └─┘          └─┘  │
 │           \ /               │ 
 │          ─ C ─              │
 │           / \               │
 └─────────────────────────────┘
```

## DEPENDENCIES

NONE
=======
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
>>>>>>> origin/main

## REFERENCES

  [1]: # ️TODO

