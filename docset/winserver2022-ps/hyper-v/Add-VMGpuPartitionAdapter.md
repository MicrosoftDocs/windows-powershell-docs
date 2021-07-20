---
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
online version:
schema: 2.0.0
---

# Add-VMGpuPartitionAdapter

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### VMName (Default)
```
Add-VMGpuPartitionAdapter [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-VMName] <String[]> [-Passthru] [-InstancePath <String>]
 [-MinPartitionVRAM <UInt64>] [-MaxPartitionVRAM <UInt64>] [-OptimalPartitionVRAM <UInt64>]
 [-MinPartitionEncode <UInt64>] [-MaxPartitionEncode <UInt64>] [-OptimalPartitionEncode <UInt64>]
 [-MinPartitionDecode <UInt64>] [-MaxPartitionDecode <UInt64>] [-OptimalPartitionDecode <UInt64>]
 [-MinPartitionCompute <UInt64>] [-MaxPartitionCompute <UInt64>] [-OptimalPartitionCompute <UInt64>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### VMObject
```
Add-VMGpuPartitionAdapter [-VM] <VirtualMachine[]> [-Passthru] [-InstancePath <String>]
 [-MinPartitionVRAM <UInt64>] [-MaxPartitionVRAM <UInt64>] [-OptimalPartitionVRAM <UInt64>]
 [-MinPartitionEncode <UInt64>] [-MaxPartitionEncode <UInt64>] [-OptimalPartitionEncode <UInt64>]
 [-MinPartitionDecode <UInt64>] [-MaxPartitionDecode <UInt64>] [-OptimalPartitionDecode <UInt64>]
 [-MinPartitionCompute <UInt64>] [-MaxPartitionCompute <UInt64>] [-OptimalPartitionCompute <UInt64>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
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
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
{{ Fill ComputerName Description }}

```yaml
Type: String[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
{{ Fill Credential Description }}

```yaml
Type: PSCredential[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstancePath
{{ Fill InstancePath Description }}

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

### -MaxPartitionCompute
{{ Fill MaxPartitionCompute Description }}

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxPartitionDecode
{{ Fill MaxPartitionDecode Description }}

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxPartitionEncode
{{ Fill MaxPartitionEncode Description }}

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxPartitionVRAM
{{ Fill MaxPartitionVRAM Description }}

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinPartitionCompute
{{ Fill MinPartitionCompute Description }}

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinPartitionDecode
{{ Fill MinPartitionDecode Description }}

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinPartitionEncode
{{ Fill MinPartitionEncode Description }}

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinPartitionVRAM
{{ Fill MinPartitionVRAM Description }}

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OptimalPartitionCompute
{{ Fill OptimalPartitionCompute Description }}

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OptimalPartitionDecode
{{ Fill OptimalPartitionDecode Description }}

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OptimalPartitionEncode
{{ Fill OptimalPartitionEncode Description }}

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OptimalPartitionVRAM
{{ Fill OptimalPartitionVRAM Description }}

```yaml
Type: UInt64
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

### -VM
{{ Fill VM Description }}

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject
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
Type: String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.HyperV.PowerShell.VirtualMachine[]

### System.String[]

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMGpuPartitionAdapter

## NOTES

## RELATED LINKS
