---
author: Kateyanne
description: 
external help file: StorSpaces2_Cmdlets.xml
manager: jasgro
Module Name: StorageSpaces
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/storagespaces/disable-storagespacesmpiosupport?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-StorageSpacesMpioSupport
---

# Disable-StorageSpacesMpioSupport

## SYNOPSIS
Prevents MPIO from claiming serial attached SCSI (SAS) disks on the local computer, and clears the default Load Balance policy configured for disks with MSDSM.
This cmdlet does not uninstall the MPIO feature.

## SYNTAX

```
Disable-StorageSpacesMpioSupport
```

## DESCRIPTION
The Disable-StorageSpacesMPIOSupport cmdlet prevents MPIO from claiming serial attached SCSI (SAS) disks on the local computer, and clears the default Load Balance policy configured for disks with MSDSM.
This cmdlet does not uninstall the MPIO feature.

## EXAMPLES

### Example 1 - Disable MPIO support on the local computer
```
PS C:\>Disable-StorageSpacesMPIOSupport
```

## PARAMETERS

## INPUTS

## OUTPUTS

### System.Boolean

### Microsoft.PowerShell.Commands.Internal.Format.FormatStartData

### Microsoft.PowerShell.Commands.Internal.Format.GroupStartData

### Microsoft.PowerShell.Commands.Internal.Format.FormatEntryData

### Microsoft.PowerShell.Commands.Internal.Format.GroupEndData

### Microsoft.PowerShell.Commands.Internal.Format.FormatEndData

## NOTES

## RELATED LINKS

