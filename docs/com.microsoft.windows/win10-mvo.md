## NAME

`WinOS Features` - Scratch pad of notes.

## DESCRIPTION

## INVOKE

### Package Management


```lang-sh
# updates packages
winget update --all
```

```lang-sh
# Reinstall all apps
Get-AppXPackage *WindowsStore* -AllUsers | Foreach {Add-AppxPackage -DisableDevelopmentMode -Register "$($_.InstallLocation)\AppXManifest.xml"}
```


### Windows Subsystem Linux

```lang-sh
# enable and upgrade feature
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

```lang-sh
# mount an additional drive
mount -t drvfs D: /mnt/d -o metadata
```
