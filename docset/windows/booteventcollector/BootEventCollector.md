---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
Module Name: BootEventCollector
Module Guid: 7E4C6113-1789-4C2D-ABAA-BEA1EF5C62E8
Download Help Link: http://go.microsoft.com/fwlink/?LinkId=518772
Help Version: 5.0.0.2
Locale: en-US
title: BootEventCollector
ms.reviewer:
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 12/20/2016
ms.topic: reference
ms.prod: w10
ms.technology: powershell-windows
ms.assetid: 394B60AC-9516-494B-86D7-50F767321820
---

# BootEventCollector Module
## Description
The Boot Event Collector module contains cmdlets to help you administer Boot Event Collector tasks in Windows Server 2016 Technical Preview.

## BootEventCollector Cmdlets
### [Checkpoint-SbecActiveConfig](./Checkpoint-SbecActiveConfig.md)
Creates a configuration checkpoint.

### [Clear-SbecProviderCache](./Clear-SbecProviderCache.md)
Clears the provider cache.

### [Disable-SbecAutologger](./Disable-SbecAutologger.md)
Disables the forwarding of events to the Setup and Boot Event Collector in the AutoLogger settings.

### [Disable-SbecBcd](./Disable-SbecBcd.md)
Disables the event forwarding mode in BCD settings.

### [Enable-SbecAutologger](./Enable-SbecAutologger.md)
Enables the forwarding of the events to the Setup and Boot Event Collector in the AutoLogger settings.

### [Enable-SbecBcd](./Enable-SbecBcd.md)
Enables and configures the event forwarding mode in the BCD settings.

### [Enable-SbecBootImage](./Enable-SbecBootImage.md)
Enables AutoLogger settings in offline WinPE Setup images.

### [Enable-SbecWdsBcd](./Enable-SbecWdsBcd.md)
Enables the BCD settings in the offline boot images imported into the WDS server.

### [Get-SbecActiveConfig](./Get-SbecActiveConfig.md)
Gets the current active configuration from the running Setup and Boot Event Collector.

### [Get-SbecBackupConfig](./Get-SbecBackupConfig.md)
Get the backup configuration files that are available to restore.

### [Get-SbecDestination](./Get-SbecDestination.md)
Get destination data files.

### [Get-SbecForwarding](./Get-SbecForwarding.md)
Gets the current connections and how data is forwarded.

### [Get-SbecHistory](./Get-SbecHistory.md)
Gets the recent history of changes in connection status.

### [Get-SbecLocalizedMessage](./Get-SbecLocalizedMessage.md)
Gets a localized message string.

### [Get-SbecLogSession](./Get-SbecLogSession.md)
Gets the running log sessions.

### [Get-SbecTraceProviders](./Get-SbecTraceProviders.md)
Gets the ETW trace providers.

### [New-SbecUnattendFragment](./New-SbecUnattendFragment.md)
Creates a fragment for Unattend.xml with post-install commands.

### [Redo-SbecActiveConfig](./Redo-SbecActiveConfig.md)
Redoes a change to the current active configuration.

### [Restore-SbecBackupConfig](./Restore-SbecBackupConfig.md)
Restores a configuration from a backup file.

### [Save-SbecInstance](./Save-SbecInstance.md)
Writes in-memory buffers to disk.

### [Save-SbecLogSession](./Save-SbecLogSession.md)
Flushes the buffers in a log session to disk.

### [Set-SbecActiveConfig](./Set-SbecActiveConfig.md)
Sets the new active configuration for the running Setup and Boot Event Collector.

### [Set-SbecLogSession](./Set-SbecLogSession.md)
Updates the settings for a log session.

### [Start-SbecInstance](./Start-SbecInstance.md)
Starts the Setup and Boot Event Collector service.

### [Start-SbecLogSession](./Start-SbecLogSession.md)
Starts an ETW log session.

### [Start-SbecNtKernelLogSession](./Start-SbecNtKernelLogSession.md)
Starts an NT Kernel Logger log session with forwarding of events to the Collector.

### [Start-SbecSimpleLogSession](./Start-SbecSimpleLogSession.md)
Starts a log session with the forwarding of events to the Collector.

### [Stop-SbecInstance](./Stop-SbecInstance.md)
Stops the Setup and Boot Event Collector.

### [Stop-SbecLogSession](./Stop-SbecLogSession.md)
Stops a log session.

### [Test-SbecActiveConfig](./Test-SbecActiveConfig.md)
Tests the active Boot Event Collector configuration.

### [Test-SbecConfig](./Test-SbecConfig.md)
Validates a configuration.

### [Undo-SbecActiveConfig](./Undo-SbecActiveConfig.md)
Reverts a change to the active configuration.



