---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
Module Name: WSUS
Module Guid: CMDLETS
Download Help Link: http://go.microsoft.com/fwlink/?linkid=390839
Help Version: 5.0.2.1
Locale: en-US
title: WSUS
ms.reviewer:
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 12/20/2016
ms.topic: reference
ms.prod: w10
ms.technology: powershell-windows
ms.assetid: D462BB6C-68B0-46A6-A3AD-2DD0523DB8BD
---

# WSUS Module
## Description
This reference provides cmdlet descriptions and syntax for all Windows Server Update Services (WSUS) Administration-specific cmdlets. It lists the cmdlets in alphabetical order based on the verb at the beginning of the cmdlet.

> [!NOTE]
> All cmdlets except the ones referencing "DynamicCategory" are included in the **UpdateServices** module.

## WSUS Cmdlets
### [Add-WsusComputer](./Add-WsusComputer.md)
Adds a client computer to a target group.

### [Add-WsusDynamicCategory](./Add-WsusDynamicCategory.md)
Adds a dynamic category to a WSUS server.

### [Approve-WsusUpdate](./Approve-WsusUpdate.md)
Approves an update to be applied to clients.

### [Deny-WsusUpdate](./Deny-WsusUpdate.md)
Declines the update for deployment.

### [Get-WsusClassification](./Get-WsusClassification.md)
Gets the list of all WSUS classifications currently available in the system.

### [Get-WsusComputer](./Get-WsusComputer.md)
Gets the WSUS computer object that represents the client computer.

### [Get-WsusDynamicCategory](./Get-WsusDynamicCategory.md)
Gets dynamic categories on a WSUS server.

### [Get-WsusProduct](./Get-WsusProduct.md)
Gets the list of all products currently available on WSUS.

### [Get-WsusServer](./Get-WsusServer.md)
Gets the WSUS update server object.

### [Get-WsusUpdate](./Get-WsusUpdate.md)
Gets the WSUS update object with details about the update.

### [Invoke-WsusServerCleanup](./Invoke-WsusServerCleanup.md)
Performs the process of cleanup on a WSUS server.

### [Remove-WsusDynamicCategory](./Remove-WsusDynamicCategory.md)
Removes a dynamic category from a WSUS server.

### [Set-WsusClassification](./Set-WsusClassification.md)
Sets whether the classifications of updates that WSUS synchronizes are enabled.

### [Set-WsusDynamicCategory](./Set-WsusDynamicCategory.md)
Sets the synchronization status of a dynamic category.

### [Set-WsusProduct](./Set-WsusProduct.md)
Sets whether the product representing the category of updates to synchronize is enabled.

### [Set-WsusServerSynchronization](./Set-WsusServerSynchronization.md)
Sets whether the WSUS server synchronizes from Microsoft Update or an upstream server.


