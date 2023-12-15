## NAME

`WinOS Registry` - Scratch pad of notes.

## DESCRIPTION

> "The Windows Registry is a hierarchical database that stores low-level settings for the Microsoft Windows operating system and for applications that opt to use the registry."s [wikipedia.org](https://en.wikipedia.org/wiki/Windows_Registry)

* [CLSID Key - Win32 apps and Registry Reference | Microsoft Learn](https://learn.microsoft.com/en-us/windows/win32/com/clsid-key-hklm)

```lang-sh
HKEY_CLASSES_ROOT (HKCR): all users default settings for this computer
HKEY_CURRENT_USER (HKCU): interactive users
HKEY_LOCAL_MACHINE (HKLM): computer specific config
HKEY_USERS (HKU): mirror of the HKEY_CURRENT_USER active profiles
HKEY_CURRENT_CONFIG (HKCC): current session runtime, not stored on disk, generated at Boot up
```