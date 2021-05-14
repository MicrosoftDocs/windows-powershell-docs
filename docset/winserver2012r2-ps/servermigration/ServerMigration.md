---
Download Help Link: https://aka.ms/winsvr-2012r2-pshelp
Help Version: {{Please enter version of help manually (X.X.X.X) format}}
Locale: en-US
Module Guid: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Module Name: ServerMigration
ms.date: 12/06/2017
title: ServerMigration
---

# ServerMigration Module
## Description
This reference provides cmdlet descriptions and syntax for all Server Migration cmdlets. It lists the cmdlets in alphabetical order based on the verb at the beginning of the cmdlet.

Administrators can use the Windows Server Migration Tools cmdlets for Windows PowerShell to migrate server roles, features, operating system settings, and other data and shares to computers that are running the latest version of Windows Server.

## ServerMigration Cmdlets
### [Export-SmigServerSetting](./Export-SmigServerSetting.md)
Exports selected Windows features and operating system settings from the local computer, and stores them in a migration store.

### [Get-SmigServerFeature](./Get-SmigServerFeature.md)
Gets the set of all Windows features that can be migrated from the local server or from a migration store.

### [Import-SmigServerSetting](./Import-SmigServerSetting.md)
Imports selected Windows features, and operating system settings from a migration store, and applies them to the local computer.

### [Receive-SmigServerData](./Receive-SmigServerData.md)
Allows a destination server to receive shares, folders, files, and associated permissions and share properties that are migrated from a source server.

### [Send-SmigServerData](./Send-SmigServerData.md)
Migrates folders, files, and associated permissions and share properties from a source server to a destination server through port 7000.

