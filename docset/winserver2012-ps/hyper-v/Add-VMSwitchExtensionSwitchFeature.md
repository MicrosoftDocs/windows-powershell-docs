---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/add-vmswitchextensionswitchfeature?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-VMSwitchExtensionSwitchFeature

## SYNOPSIS
Adds a feature to a virtual switch.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-VMSwitchExtensionSwitchFeature [-SwitchName] <String[]> [-ComputerName <String[]>] [-Passthru]
 -VMSwitchExtensionFeature <VMSwitchExtensionSwitchFeature[]>
```

### UNNAMED_PARAMETER_SET_2
```
Add-VMSwitchExtensionSwitchFeature [-VMSwitch] <VMSwitch[]> [-Passthru]
 -VMSwitchExtensionFeature <VMSwitchExtensionSwitchFeature[]>
```

## DESCRIPTION
The **Add-VMSwitchExtensionSwitchFeature** cmdlet adds a feature supported by a virtual switch extension to a virtual switch.

## EXAMPLES

### Example 1
```
PS C:\>$feature = Get-VMSwitchExtensionSwitchFeature -FeatureName "Ethernet Switch BandwidthSettings"
PS C:\>$feature.SettingData.DefaultFlowReservation = 300000000
PS C:\>Add-VMSwitchExtensionSwitchFeature "External" -VMSwitchExtensionSwitchFeature $feature
```

Adds a feature to virtual switch External.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which a feature is to be added to a virtual switch.
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
Specifies that an object is to be passed through to the pipeline representing the feature to be added.

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
Specifies the name of the virtual switch to which the feature is to be added.

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
Specifies the virtual switch to which the feature is to be added.

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
Specifies the feature to be added to the virtual switch.

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



