---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Get-PhysicalExtent

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByVirtualDisk
```
Get-PhysicalExtent -VirtualDisk <CimInstance> [-CimSession <CimSession>] [<CommonParameters>]
```

### ByStorageTier
```
Get-PhysicalExtent -StorageTier <CimInstance> [-CimSession <CimSession>] [<CommonParameters>]
```

### ByPhysicalDisk
```
Get-PhysicalExtent -PhysicalDisk <CimInstance> [-CimSession <CimSession>] [<CommonParameters>]
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
Type: CimSession
Parameter Sets: (All)
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
Type: CimInstance
Parameter Sets: ByPhysicalDisk
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageTier
{{ Fill StorageTier Description }}

```yaml
Type: CimInstance
Parameter Sets: ByStorageTier
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualDisk
{{ Fill VirtualDisk Description }}

```yaml
Type: CimInstance
Parameter Sets: ByVirtualDisk
Aliases:

Required: True
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
