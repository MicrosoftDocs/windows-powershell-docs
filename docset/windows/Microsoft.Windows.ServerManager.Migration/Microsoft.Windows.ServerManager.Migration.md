---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
Module Name: Microsoft.Windows.ServerManager.Migration
Module Guid:
ms.topic: reference
manager: jasgro
author: andreabarr
ms.prod: w10
ms.assetid: 02BBB040-10B1-4771-B928-EA4DA6E5D54F
keywords: powershell, cmdlet
ms.date: 2017-01-03
title: Microsoft.Windows.ServerManager.Migration
ms.reviewer:
ms.technology: powershell-windows
---


# Microsoft.Windows.ServerManager.Migration Module
## Description
This reference provides cmdlet descriptions and syntax for all Server Migration cmdlets. It lists the cmdlets in alphabetical order based on the verb at the beginning of the cmdlet.

Administrators can use the Windows Server Migration Tools cmdlets for Windows PowerShell to migrate server roles, features, operating system settings, and other data and shares to computers that are running the latest version of Windows Server.

## Microsoft.Windows.ServerManager.Migration Cmdlets
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

