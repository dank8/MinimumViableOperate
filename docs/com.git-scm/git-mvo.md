## NAME
 git, a minimum viable operating instruction for package git 

## SYNOPSIS

```lang-sh
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

```lang-sh
git config --global credential.helper wincred`

git credential fill
protocol=https
host=github.com
username=<username>
password=<password>
```

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

```
 ┌────────────────────────────────────────────────────────────────────────────┐
 │  ┌───────────── 'ORIGIN' REPOSITORY ──┐                                    │
 │  │ ************                       │                                    │
 │  │ * Branch1  *                       │                                    │
 │  │ * ┌─┐  ┌─┐ *                       │                                    │
 │  │ * │A├─►│B│ *                       │                                    │
 │  │ * └─┘  └┬┘ *                       │                                    │
 │  │ ********│***                       │                                    │
 │  │         │                          │                                    │
 │  │      ***│************************* │                                    │
 │  │      *  │   Branch2   ┌─┐        * │                                    │
 │  │      *  │             │E├─┐      * │                                    │
 │  │      * ┌▼┐  ┌─┐  ┌─┬─►└─┘ │  ┌─┐ * │                                    │
 │  │      * │A├─►│C├─►│D│      ├─►│I│ * │               ┌─                   │
 │  │      * └─┘  └─┘  └┬┴─►┌─┐ │  └─┘ * │               │  ┌──────────┐      │
 │  │      *            │   │G├─┘      * │               │  │git commit│    ┐ │
 │  │      *            │   └─┘        * │               │ ┌▼┐     ┌───┴──┐ │ │
 │  │      *************│*************** │               │ │H│     │STAGED│ │ │
 │  │                   │                │               │ └┬┘     └───▲──┘ │ │ 
 │  │                 **│************ ───┘               └──│─STAGING─ │────┘ │
 │  │                 * │Branch3    *                       │          │      │
 │  │                 *┌▼┐  ┌─┐  ┌┐ *               git push│          │      │
 │  │                 *│D├─►│F│  │◄─────────────────────────┘          │      │
 │  │                 *└─┘  └┬┘  └┘ *          ┌ WORKING TREE ┐        │      │
 │  └─────────────────*******│*******          │  FolderA     │        │      │
 │                           │                 │  ├file1      │        │      │
 │                           │git clone ┌HEAD┐ │  └FolderB    │git add │      │
 │                           └─────────►│ D  ├─┤   └file3     ├────────┘      │
 │                                      └────┘ └   └file4     ┘               │
 └────────────────────────────────────────────────────────────────────────────┘
```

### Fundamentals of making changes 

```lang-sh
# choose the branch you want to edit in the Work Tree (file system)
git switch origin <branchName>
```

```lang-sh
# download the latest changes from ORIGIN
git pull --all
```

```lang-sh
# create commit
git commit -a -m <commit message text>
```

```lang-sh
# check the status for any missed changes
git status
```

```lang-sh
# Send commit snapshots to the remote repository
git push origin
```

### Viewing History

```
git log --graph
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

```
 ┌─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┐
 │   ┌─────────────────────────────────────────────────────┐                                                                   │
 │   │                 Local File System                   │                                                                   │
 │   └─┬───────────────┬───────┬──────────────────────┬────┘        ┌────────┐                                                 │
 │     │   Work Tree   │       │    GIT REPOSITORY    │             │ Remote │                                                 │
 │     └───────┬───────┘       └───────────────────┬──┘             └───┬────┘                                                 │
 │             │                                   │                    │    REPOSITORY LIFECYCLE                              │
 │             │                                   │                    │                                                      │
 │             │                                   │           git clone│    1. Create the local repository                    │
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
 │             │◄──────────────────────────────────┤◄───────────────────┤         Fetch the latest remote repository commits   │
 │             │                                   │                    │                                                      │
 │             │ git commit -a -m                  │                    │    2. git commit -a -m <message>                     │
 │             ├──────────────────────────────────►│                    │         commits all working directory changes.       │
 │             │                                   │                    │         simple process does not stage files.         │
 │             │            git status             │                    │    3. git status                                     │
 │             │◄─────────────────────────────────►│                    │         list status of each file                     │
 │             │                                   │                    │         (unstaged > staged > committed)              │
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
 │             │                  │                │                    │         keep version history with the new file.      │
 │             │ git reset        │                │                    │                                                      │
 │             │ git restore      │                │                    │    3. git restore                                    │
 │             │◄─────────────────┤                │                    │        Remove staging index, changes 'unstaged'      │
 │             │                  │                │                    │        does not alter the work tree files            │
 │             │                  │ git commit -m  │                    │    4. git commit -m <message text>                   │
 │             │                  ├───────────────►│                    │         create snapshot ready for remote repository  │
 │             │                  │                │                    │         NOTE: --ammend will append to previous commit│
 │             │ git stash push   │                │                    │    5. git stash push -m <message>                    │
 │             │◄────────────────►│                │                    │         staged changes stored locally with message   │
 │             │◄────────────────►│                │                    │         staged changes stored locally with message   │
 │             │ git stash list   │                │                    │    6. git stash list                                 │
 │             │      ───────────►│                │                    │         list of all stashed changes                  │
 │             │ git stash apply  │                │                    │    7. git stash apply <stashName                     │
 │             │◄─────────────────┤                │                    │         remove all changes from working Tree         │
 │             │                  │                │                    │         restore named stash                          │
 │             │                                   │    git fetch       │    8. git fetch <remote>                             │
 │             │                                   ├───────────────────►│         downloads all data from remote repository    │
 │             │                                   │                    │                                                      │
 │             │                        git switch │                    │    9. git switch origin <branch>                     │
 │             │◄──────────────────────────────────┤                    │         update work tree files to another branch     │
 │             │                                   │                    │                                                      │
 │             │                        git rebase │                    │                                                      │
 │             │                         git merge │                    │   10. git merge <branch>                             │
 │             │                       ┌───────────┤                    │         add changes from another branch to work Tree │
 │             │◄──────────────────────┤           │                    │                                                      │
 │             │                       └───────────┤                    │                                                      │
 │             │                                   │                    │                                                      │
 │             │                  git bisect start │                    │                                                      │
 │             │                    git bisect bad │                    │                                                      │
 │             │                   git bisect good │                    │  11. git bisect                                      │
 │             │                       ┌───────────┤                    │         semi-automated fetch of specific versions    │
 │             │◄──────────────────────┤           │                    │         Assist in identifying version with bug.      │
 │             │                       └───────────┤                    │                                                      │
 └─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┘
```

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


### Revert, Restore, Reset

`git revert` reverse the effect of an earlier commit

```
 ┌──────────────────────┐
 │ Branch2              │
 │ ┌─┐  ┌─┐  ┌─┐  ┌──┐  │
 │ │A├─►│B├─►│D├─►│!B│  │
 │ └─┘  └.┘  └─┘  └.─┘  │
 │       ...........    │ 
 │                      │
 │                      │
 └──────────────────────┘
```

`git reset` remove staged or unstaged differences from local storage. 
Optionally specify a <commit> index to change the local HEAD to a different commit

```
 ┌─────────────────┬───────┬───────────┬───────┬─────────────────────────────┐
 │                 │ HEAD  │  WORKING  │STAGING│                             │
 │ Branch2         │       │   TREE    │       │                             │
 │ ┌─┐  ┌─┐  ┌─┐   │  ┌─┐  │  ┌─┐ ┌─┐  │  ┌─┐  │                             │
 │ │A├─►│B├─►│D├───┼──┤D│  │  │D│∪│Δ│  │  │E│  │ local storage begin state   │
 │ └─┘  └─┘  └─┘   │  └─┘  │  └─┘ └─┘  │  └─┘  │                             │

 │ ┌─┐  ┌─┐  ┌─┐   │  \ /  │  ┌─┐ ┌─┐  │  ┌─┐  │                             │
 │ │A├─►│B├─►│D│   │ ─ D ─ │  │D│∪│Δ│  │  │E│  │ git reset --soft <commit>   │
 │ └─┘  └┬┘  └─┘   │  / \  │  └─┘ └─┘  │  └─┘  │   - Change HEAD only        │
 │       │         │  ┌─┐  │           │       │                             │
 │       └─────────┼──┤B│  │           │       │                             │
 │                 │  └─┘  │           │       │                             │

 │ ┌─┐  ┌─┐  ┌─┐   │  \ /  │  \ /      │  \ /  │                             │
 │ │A├─►│B├─►│D│   │ ─ D ─ │ ─ D ─     │ ─ E ─ │                             │
 │ └─┘  └┬┘  └─┘   │  / \  │  / \      │  / \  │  git reset --merge <commit> │
 │       │         │  ┌─┐  │  ┌─┐ ┌─┐  │       │   - Carries forward staged  │
 │       └─────────┼──┤B│  │  │B│∪│Δ│  │       │     and unstaged changes    │
 │                 │  └─┘  │  └─┘ └─┘  │       │                             │

 │ ┌─┐  ┌─┐  ┌─┐   │  \ /  │  \ / \ /  │  \ /  │                             │
 │ │A├─►│B├─►│D│   │ ─ D ─ │ ─ D ─ Δ ─ │ ─ E ─ │                             │
 │ └─┘  └┬┘  └─┘   │  / \  │  / \ / \  │  / \  │   git reset --hard <commit> │
 │       │         │  ┌─┐  │  ┌─┐      │       │    - removes staged         │
 │       └─────────┼──┤B│  │  │B│      │       │      and unstaged changes   │
 │                 │  └─┘  │  └─┘      │       │                             │ 
 └─────────────────┴───────┴───────────┴───────┴─────────────────────────────┘
```

`git restore --source=<tree>` revert a specific sub-path in the working tree to the HEAD. 


## DEPENDENCIES

NONE

## REFERENCES

  [1]: # ️TODO

