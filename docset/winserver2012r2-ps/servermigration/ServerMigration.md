---
Module Name: ServerMigration
Module Guid: XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
Download Help Link: {{Please enter FwLink manually}}
Help Version: {{Please enter version of help manually (X.X.X.X) format}}
Locale: en-US
title: ServerMigration
description: 
keywords: powershell, cmdlet
author: biranlic
manager: jasgro
ms.date: 2017-12-06
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: f26a956e-b0fa-4e44-b11e-553d97b25f1d
ms.manager: dansimp
ms.reviewer:
ms.author: kenwith
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

