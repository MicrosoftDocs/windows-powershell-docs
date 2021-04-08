---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmswitchextensionswitchfeature?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMSwitchExtensionSwitchFeature

## SYNOPSIS
Gets the features configured on a virtual switch.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMSwitchExtensionSwitchFeature [-SwitchName] <String[]> [-ComputerName <String[]>]
 [-Extension <VMSwitchExtension[]>] [-ExtensionName <String[]>] [-FeatureId <Guid[]>] [-FeatureName <String[]>]
 [-Passthru] -VMSwitchExtensionFeature <VMSwitchExtensionSwitchFeature[]>
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMSwitchExtensionSwitchFeature [-VMSwitch] <VMSwitch[]> [-Extension <VMSwitchExtension[]>]
 [-ExtensionName <String[]>] [-FeatureId <Guid[]>] [-FeatureName <String[]>] [-Passthru]
 -VMSwitchExtensionFeature <VMSwitchExtensionSwitchFeature[]>
```

## DESCRIPTION
The **Get-VMSwitchExtensionSwitchFeature** cmdlet gets the features configured on a virtual switch.
The object can be used to update the configuration of the switch using the Set-VmSwitchExtensionFeature command.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMSwitchExtensionSwitchFeature
```

ps_miss_tech_content

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the features configured on a virtual switch are to be retrieved.
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

### -Extension
Specifies the virtual switch extension.

```yaml
Type: VMSwitchExtension[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtensionName
Specifies the name of the virtual switch extension.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FeatureId
Specifies the unique identifier of the feature.

```yaml
Type: Guid[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FeatureName
Specifies the name of the feature.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.VMSwitchExtensionSwitchFeature** object is to be passed through to the pipeline representing the features to be retrieved.

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
Specifies the feature to be retrieved.

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

## NOTES

## RELATED LINKS



