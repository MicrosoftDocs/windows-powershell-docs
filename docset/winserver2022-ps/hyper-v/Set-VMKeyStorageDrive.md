---
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
online version:
schema: 2.0.0
---

# Set-VMKeyStorageDrive

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### VMName (Default)
```
Set-VMKeyStorageDrive [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String> [[-ControllerNumber] <Int32>] [[-ControllerLocation] <Int32>] [-ToControllerNumber <Int32>]
 [-ToControllerLocation <Int32>] [-ResourcePoolName <String>] [-AllowUnverifiedPaths] [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Object
```
Set-VMKeyStorageDrive [-VMKeyStorageDrive] <KeyStorageDrive[]> [-ToControllerNumber <Int32>]
 [-ToControllerLocation <Int32>] [-ResourcePoolName <String>] [-AllowUnverifiedPaths] [-Passthru] [-WhatIf]
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

### -AllowUnverifiedPaths
{{ Fill AllowUnverifiedPaths Description }}

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

### -ControllerLocation
{{ Fill ControllerLocation Description }}

```yaml
Type: Int32
Parameter Sets: VMName
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerNumber
{{ Fill ControllerNumber Description }}

```yaml
Type: Int32
Parameter Sets: VMName
Aliases:

Required: False
Position: 1
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

### -ResourcePoolName
{{ Fill ResourcePoolName Description }}

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

### -ToControllerLocation
{{ Fill ToControllerLocation Description }}

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToControllerNumber
{{ Fill ToControllerNumber Description }}

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMKeyStorageDrive
{{ Fill VMKeyStorageDrive Description }}

```yaml
Type: KeyStorageDrive[]
Parameter Sets: Object
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
Type: String
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
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

### Microsoft.HyperV.PowerShell.KeyStorageDrive[]

## OUTPUTS

### Microsoft.HyperV.PowerShell.KeyStorageDrive

## NOTES

## RELATED LINKS
