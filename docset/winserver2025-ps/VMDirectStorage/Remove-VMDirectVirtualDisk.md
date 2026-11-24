---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/vmdirectstorage/remove-vmdirectvirtualdisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VMDirectVirtualDisk
---

# Remove-VMDirectVirtualDisk

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByVMName
```
Remove-VMDirectVirtualDisk [-VMName] <String> [-CimSession <CimSession[]>] [-ControllerType] <ControllerType>
 [-ControllerNumber] <Int32> [-ControllerLocation] <Int32> [<CommonParameters>]
```

### ByVirtualDisk
```
Remove-VMDirectVirtualDisk [-VirtualDisk] <VMDirectVirtualDisk[]> [<CommonParameters>]
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

### -CimSession
{{ Fill CimSession Description }}

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ByVMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerLocation
{{ Fill ControllerLocation Description }}

```yaml
Type: System.Int32
Parameter Sets: ByVMName
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerNumber
{{ Fill ControllerNumber Description }}

```yaml
Type: System.Int32
Parameter Sets: ByVMName
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerType
{{ Fill ControllerType Description }}

```yaml
Type: ControllerType
Parameter Sets: ByVMName
Aliases:
Accepted values: SCSI

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDisk
{{ Fill VirtualDisk Description }}

```yaml
Type: VMDirectVirtualDisk[]
Parameter Sets: ByVirtualDisk
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
{{ Fill VMName Description }}

```yaml
Type: System.String
Parameter Sets: ByVMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### VMDirectVirtualDisk[]

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
