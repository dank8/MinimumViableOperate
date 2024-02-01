## NAME
 vi, a minimum viable operating instruction for package vi 

## SYNOPSIS

```lang-sh
 # Generic invocation
gh [OPTIONS]
```

## DESCRIPTION
A working example of minimum syntax commands for using vi text editor.

> QUOTE FROM DEVELOPER

## INSTALLATION

NONE

## INVOKE

| key | Action |
|:--:|:-- | 	 
| I | enter Insert mode, at beginning of line |
| i | enter Insert mode, at cursor |
| a | enter Insert mode, append after cursor |
| A | enter Insert mode, Append at line end |
| yy | copy current line|
| p | paste clipboard ABOVE current line |
| P | paste clipboard BELOW current line |
| u | undo last command |
| Esc | Exit Insert mode |

| key | Action |
|:--:|:-- | 
| ? {string} | search backwards |
| / {string} | search fowardwards |

| Esc | Exit Insert mode |
 	 	
Save and Quit (command mode):

| key | Action |
|:--:|:-- | 	 	
| : | Enter Command Mode | 
| :w | Save changes to buffer |
| :wq | Save changes and quit |
| :w | file Save file to new file |
| :q! | Quit without saving |
| :[%]s/{oldstr}/{newstr}/[c][g] | string replace. optional parameters [%]=entire file [c]=confirm [g]=global |
| Esc | Exit mode |



## EXPLANATORY NOTES

1. source: [ss64](https://ss64.com/vi.html)

## DEPENDENCIES

NONE