---
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
online version:
schema: 2.0.0
---

# Remove-VMHostAssignableDevice

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### Path (Default)
```
Remove-VMHostAssignableDevice [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-InstancePath <String>] [-LocationPath <String>] -ResourcePoolName <String[]>
 [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object
```
Remove-VMHostAssignableDevice [-HostAssignableDevice] <VMHostAssignableDevice[]> -ResourcePoolName <String[]>
 [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
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
Parameter Sets: Path
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
Parameter Sets: Path
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
Parameter Sets: Path
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
{{ Fill Force Description }}

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

### -HostAssignableDevice
{{ Fill HostAssignableDevice Description }}

```yaml
Type: VMHostAssignableDevice[]
Parameter Sets: Object
Aliases: VMHostAssignableDevice

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InstancePath
{{ Fill InstancePath Description }}

```yaml
Type: String
Parameter Sets: Path
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocationPath
{{ Fill LocationPath Description }}

```yaml
Type: String
Parameter Sets: Path
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
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
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

### Microsoft.HyperV.PowerShell.VMHostAssignableDevice[]

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
