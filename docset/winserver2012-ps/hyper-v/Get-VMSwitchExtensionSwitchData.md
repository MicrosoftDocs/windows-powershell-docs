---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Get-VMSwitchExtensionSwitchData

## SYNOPSIS
Gets the status of a virtual switch extension feature applied on a virtual switch.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMSwitchExtensionSwitchData [-SwitchName] <String[]> [-ComputerName <String[]>]
 [-Extension <VMSwitchExtension[]>] [-ExtensionName <String[]>] [-FeatureId <Guid[]>] [-FeatureName <String[]>]
 [-Passthru] -VMSwitchExtensionFeature <VMSwitchExtensionSwitchFeature[]>
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMSwitchExtensionSwitchData [-VMSwitch] <VMSwitch[]> [-Extension <VMSwitchExtension[]>]
 [-ExtensionName <String[]>] [-FeatureId <Guid[]>] [-FeatureName <String[]>] [-Passthru]
 -VMSwitchExtensionFeature <VMSwitchExtensionSwitchFeature[]>
```

## DESCRIPTION
The **Get-VMSwitchExtensionSwitchData** cmdlet gets the status of a virtual switch extension applied on a virtual switch.
This switch feature data surfaces runtime information and statistics on a per-switch basis.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMSwitchExtensionSwitchData External -FeatureId 1c37e01c-0cd6-496f-9076-90c131033dc2
```

Gets the switch data from a virtual switch extension that is configured on virtual switch External.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the status of a virtual switch extension is to be retrieved.
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
Specifies the virtual switch extension for which status is to be retrieved.

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
Specifies the name of the virtual switch extension for which status is to be retrieved.

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
Specifies the unique identifier of a feature supported by the virtual switch extension.

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
Specifies the name of a feature supported by the virtual switch extension.

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
Specifies that an **Microsoft.Virtualization.PowerShell.VMSwitchExtensionSwitchData** object is to be passed through to the pipeline representing the virtual switch extension status.

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
Specifies the virtual switch extension feature.

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

[00000000-0000-0000-0000-000000000000](00000000-0000-0000-0000-000000000000)

