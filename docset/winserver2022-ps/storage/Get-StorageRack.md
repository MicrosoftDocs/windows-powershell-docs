---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 08/30/2021
online version: https://docs.microsoft.com/powershell/module/storage/get-storagerack?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StorageRack
---

# Get-StorageRack

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### EnumerateFaultDomains (Default)
```
Get-StorageRack [-FriendlyName <String>] [-SerialNumber <String>] [-PhysicalLocation <String>]
 [-CimSession <CimSession>] [<CommonParameters>]
```

### ByStorageSubsystem
```
Get-StorageRack -StorageSubsystem <CimInstance> [-FriendlyName <String>] [-SerialNumber <String>]
 [-PhysicalLocation <String>] [-CimSession <CimSession>] [<CommonParameters>]
```

### ByStorageFaultDomain
```
Get-StorageRack -StorageFaultDomain <CimInstance> [-FriendlyName <String>] [-SerialNumber <String>]
 [-PhysicalLocation <String>] [-CimSession <CimSession>] [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
{{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
{{ Fill FriendlyName Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalLocation
{{ Fill PhysicalLocation Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SerialNumber
{{ Fill SerialNumber Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageFaultDomain
{{ Fill StorageFaultDomain Description }}

```yaml
Type: CimInstance
Parameter Sets: ByStorageFaultDomain
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubsystem
{{ Fill StorageSubsystem Description }}

```yaml
Type: CimInstance
Parameter Sets: ByStorageSubsystem
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
