---
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
online version:
schema: 2.0.0
---

# Set-VMPartitionableGpu

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ComputerName (Default)
```
Set-VMPartitionableGpu [[-ComputerName] <String[]>] [[-Credential] <PSCredential[]>] [-Passthru]
 [-PartitionCount <UInt16>] [<CommonParameters>]
```

### CimSession
```
Set-VMPartitionableGpu [-CimSession] <CimSession[]> [-Passthru] [-PartitionCount <UInt16>] [<CommonParameters>]
```

### Object
```
Set-VMPartitionableGpu [-PartitionableGpu] <VMPartitionableGpu[]> [-Passthru] [-PartitionCount <UInt16>]
 [<CommonParameters>]
```

### Name
```
Set-VMPartitionableGpu [-Passthru] [-Name <String>] [-PartitionCount <UInt16>] [<CommonParameters>]
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
Type: CimSession[]
Parameter Sets: CimSession
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
{{ Fill ComputerName Description }}

```yaml
Type: String[]
Parameter Sets: ComputerName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
{{ Fill Credential Description }}

```yaml
Type: PSCredential[]
Parameter Sets: ComputerName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
{{ Fill Name Description }}

```yaml
Type: String
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionableGpu
{{ Fill PartitionableGpu Description }}

```yaml
Type: VMPartitionableGpu[]
Parameter Sets: Object
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PartitionCount
{{ Fill PartitionCount Description }}

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
{{ Fill Passthru Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimSession[]

### Microsoft.HyperV.PowerShell.VMPartitionableGpu[]

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMPartitionableGpu

## NOTES

## RELATED LINKS
