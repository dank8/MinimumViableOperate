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

1. git-scm.com

### INVOKE

- `--global` applies for all repos for the current user
- `--system` applies for all users in the system
- `--local` applies for a specific repo

#### Configure user

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

#### Create repo
```lang-sh
cd {ReposRootfolder}
git init
```

#### Clone Remote content

```lang-sh
git clone {url}
```

#### Status of Repos

```lang-sh
$ COMMAND
OUTPUT
```

### EXPLANATORY NOTES

1. # ️TODO

## DEPENDENCIES

PACKAGE == VERSION

## REFERENCES

  [1]: # ️TODO

