---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-VMSwitchExtensionSwitchFeature

## SYNOPSIS
Configures a feature on a virtual switch.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VMSwitchExtensionSwitchFeature [-SwitchName] <String[]> [-ComputerName <String[]>] [-Passthru]
 -VMSwitchExtensionFeature <VMSwitchExtensionSwitchFeature[]>
```

### UNNAMED_PARAMETER_SET_2
```
Set-VMSwitchExtensionSwitchFeature [-VMSwitch] <VMSwitch[]> [-Passthru]
 -VMSwitchExtensionFeature <VMSwitchExtensionSwitchFeature[]>
```

## DESCRIPTION
The **Set-VMSwitchExtensionSwitchFeature** cmdlet configures a feature on a virtual switch.
The feature must have already been configured on the virtual switch.

## EXAMPLES

### Example 1
```
PS C:\>$feature = Get-VMSystemSwitchExtensionSwitchFeature -FeatureName "Ethernet Switch Bandwidth Settings"
PS C:\>$feature.SettingData.DefaultFlowReservation = 100000000
PS C:\>Set-VMSwitchExtensionSwitchFeature External $feature
```

Configures the feature on virtual switch External.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which a feature is to be configured.
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
Specifies that a **Microsoft.HyperV.PowerShell.VMSwitchExtensionSwitchFeature** is to be passed through to the pipeline representing the feature to be configured.

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
Specifies the name of the virtual switch.

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
Specifies the virtual switch.

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
Specifies the feature to be configured.

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

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.HyperV.PowerShell.VMSwitchExtensionSwitchFeature
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



