---
external help file: StorSpaces2_Cmdlets.xml
Module Name: StorageSpaces
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/storagespaces/enable-storagespacesmpiosupport?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-StorageSpacesMpioSupport
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

