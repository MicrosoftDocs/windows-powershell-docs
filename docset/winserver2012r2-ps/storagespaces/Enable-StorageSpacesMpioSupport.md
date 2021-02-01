---
external help file: StorSpaces2_Cmdlets.xml
online version: 
schema: 2.0.0
title: Enable-StorageSpacesMpioSupport
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: F5298113-A139-4CFB-85BC-91038FF74E7B
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Enable-StorageSpacesMpioSupport

## SYNOPSIS
Installs and optimizes the configuration of MPIO for Storage Spaces with serial attached SCSI (SAS) disks on the local computer.

## SYNTAX

```
Enable-StorageSpacesMpioSupport
```

## DESCRIPTION
The Disable-StorageSpacesMPIOSupport cmdlet installs and optimizes the configuration of MPIO for Storage Spaces with serial attached SCSI (SAS) disks on the local computer.
If the MPIO feature is not installed, this cmdlet will install MPIO, and configure MPIO to automatically claim all SAS disks, and configure the default MPIO load balance policy for Round Robin.
This command may require a restart if SAS disks are already present in the system.

## EXAMPLES

### Example 1 - Enable MPIO support on the local computer
```
PS C:\>Enable-StorageSpacesMPIOSupport
```

## PARAMETERS

## INPUTS

### None

## OUTPUTS

### Microsoft.Dism.Commands.ImageObject

### Microsoft.Management.Infrastructure.CimInstance#root/microsoft/windows/storage/MSFT_MSDSMSupportedHW

### System.Boolean

### Microsoft.PowerShell.Commands.Internal.Format.FormatStartData

### Microsoft.PowerShell.Commands.Internal.Format.GroupStartData

### Microsoft.PowerShell.Commands.Internal.Format.FormatEntryData

### Microsoft.PowerShell.Commands.Internal.Format.GroupEndData

### Microsoft.PowerShell.Commands.Internal.Format.FormatEndData

## NOTES

## RELATED LINKS

