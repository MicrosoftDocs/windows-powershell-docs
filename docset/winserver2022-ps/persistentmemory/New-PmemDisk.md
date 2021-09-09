---
external help file: Microsoft.Storage.PersistentMemory.Management.Commands.dll-Help.xml
Module Name: PersistentMemory
online version:
schema: 2.0.0
---

# New-PmemDisk

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### NormalDisk
```
New-PmemDisk -RegionId <UInt32[]> [-FriendlyName <String[]>] [-DiskSizeInBytes <UInt64[]>]
 [-AtomicityType <NAMESPACE_ATOMICITY_TYPE[]>] [<CommonParameters>]
```

### SimulatedDisk
```
New-PmemDisk -DiskSizeInBytes <UInt64[]> [-AtomicityType <NAMESPACE_ATOMICITY_TYPE[]>] [-Simulated]
 [<CommonParameters>]
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

### -AtomicityType
{{ Fill AtomicityType Description }}

```yaml
Type: NAMESPACE_ATOMICITY_TYPE[]
Parameter Sets: (All)
Aliases:
Accepted values: None, BlockTranslationTable

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskSizeInBytes
{{ Fill DiskSizeInBytes Description }}

```yaml
Type: UInt64[]
Parameter Sets: NormalDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: UInt64[]
Parameter Sets: SimulatedDisk
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
{{ Fill FriendlyName Description }}

```yaml
Type: String[]
Parameter Sets: NormalDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RegionId
{{ Fill RegionId Description }}

```yaml
Type: UInt32[]
Parameter Sets: NormalDisk
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Simulated
{{ Fill Simulated Description }}

```yaml
Type: SwitchParameter
Parameter Sets: SimulatedDisk
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.UInt32[]

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
