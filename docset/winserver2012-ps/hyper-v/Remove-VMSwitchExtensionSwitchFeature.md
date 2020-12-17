---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Remove-VMSwitchExtensionSwitchFeature

## SYNOPSIS
Removes a feature from a virtual switch.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-VMSwitchExtensionSwitchFeature [-SwitchName] <String[]> [-ComputerName <String[]>] [-Passthru]
 -VMSwitchExtensionFeature <VMSwitchExtensionSwitchFeature[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-VMSwitchExtensionSwitchFeature [-VMSwitch] <VMSwitch[]> [-Passthru]
 -VMSwitchExtensionFeature <VMSwitchExtensionSwitchFeature[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-VMSwitchExtensionSwitchFeature** removes a feature from a virtual switch.
The feature already must have been configured on the virtual switch.

## EXAMPLES

### Example 1
```
PS C:\>$feature = Get-VMSwitchExtensionSwitchFeature -SwitchName External -FeatureId 3eb2b8e8-4abf-4dbf-9071-16dd47481fbe
PS C:\>Remove-VMSwitchExtensionSwitchFeature External $feature
```

Removes a feature from virtual switch External.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which the feature is to be removed.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.VMSwitchExtensionSwitchFeature** is to be passed through to the pipeline representing the feature to be removed.

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

### -SwitchName
Specifies the name of the virtual switch from which the feature is to be removed.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMSwitch
Specifies the virtual switch from which the feature is to be removed.

```yaml
Type: VMSwitch[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMSwitchExtensionFeature
Specifies the feature to be removed.

```yaml
Type: VMSwitchExtensionSwitchFeature[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.HyperV.PowerShell.VMSwitchExtensionSwitchFeature
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



