---
external help file: Microsoft.Windows.HardenedFabric.Cmdlets.dll-Help.xml
Module Name: ShieldedVMDataFile
online version: 
schema: 2.0.0
---

# Save-ShieldedVMRecoveryKey

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### VHDParameterSet (Default)
```
Save-ShieldedVMRecoveryKey -VHDPath <String> -Path <String> [-Force] [-WhatIf] [-Confirm]
```

### DiskNumberParameterSet
```
Save-ShieldedVMRecoveryKey -DiskNumber <Int32> -Path <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -DiskNumber
{{Fill DiskNumber Description}}

```yaml
Type: Int32
Parameter Sets: DiskNumberParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
{{Fill Force Description}}

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

### -Path
{{Fill Path Description}}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VHDPath
{{Fill VHDPath Description}}

```yaml
Type: String
Parameter Sets: VHDParameterSet
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

## INPUTS

### None


## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

