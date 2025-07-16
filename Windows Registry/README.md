# Core Windows Registry Hives and Their Forensic Value

## NTUSER.DAT

| **Category**       | **Details**                                 |
| ------------------ | ------------------------------------------- |
| **Location**       | `C:\Users\<username>\NTUSER.DAT`            |
| **Loaded Under**   | `HKEY_USERS\<SID>`                          |
| **Forensic Value** | Tracks user-specific settings and activity. |

| **Registry Key / Entry**          | **Description**                                                                         |
| --------------------------------- | --------------------------------------------------------------------------------------- |
| **UserAssist**                    | Tracks program execution for GUI apps or LNK files launched via the Windows UI.         |
| **RunMRU**                        | Tracks commands executed via the Windows Run dialog.                                    |
| **OpenSaveMRU**                   | Tracks files opened or saved via Windows Open/Save dialog.                              |
| **OfficeMRU**                     | Tracks most recently used files for each Office app (Word, Excel, PowerPoint, etc.).    |
| **LastVisitedMRU**                | Tracks applications that used Open/Save dialog and last location accessed for each.     |
| **RecentDocs**                    | Tracks recently accessed files and folders, used to populate “Recent” lists in Windows. |
| **WordWheelQuery**                | Tracks search strings entered in Windows File Explorer search box.                      |
| **TypedPaths**                    | Tracks paths directly typed into the File Explorer path bar.                            |
| **ShellBags**                     | Includes UNC path data; shows evidence of folders users have opened.                    |
| **MountPoints2**                  | Tracks mounted USB devices and network shares.                                          |
| **User-specific Installed Apps**  | Tracks apps installed specifically for the user (not system-wide).                      |
| **User-specific Autorun Entries** | Contains user-specific persistence keys (e.g., Run/RunOnce).                            |
