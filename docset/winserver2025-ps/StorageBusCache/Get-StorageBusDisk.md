---
external help file: StorageBusCache-help.xml
Module Name: StorageBusCache
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/storagebuscache/get-storagebusdisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StorageBusDisk
---

# Get-StorageBusDisk

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByGuid (Default)
```
Get-StorageBusDisk [-Guid <String>] [<CommonParameters>]
```

### ByNumber
```
Get-StorageBusDisk [-Number <UInt32>] [<CommonParameters>]
```

### ByPhysicalDisk
```
Get-StorageBusDisk [-PhysicalDisk <CimInstance>] [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -Guid
{{ Fill Guid Description }}

```yaml
Type: System.String
Parameter Sets: ByGuid
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Number
{{ Fill Number Description }}

```yaml
Type: System.UInt32
Parameter Sets: ByNumber
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalDisk
{{ Fill PhysicalDisk Description }}

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: ByPhysicalDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
