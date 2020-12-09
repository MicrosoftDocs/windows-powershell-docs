---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-VMSystemSwitchExtensionPortFeature

## SYNOPSIS
Gets the port-level features supported by virtual switch extensions on one or more Hyper-V hosts.

## SYNTAX

```
Get-VMSystemSwitchExtensionPortFeature [-ComputerName <String[]>] [-ExtensionName <String[]>]
 [-FeatureId <Guid[]>] [-FeatureName <String[]>] [-SystemSwitchExtension <VMSystemSwitchExtension[]>]
```

## DESCRIPTION
The **Get-VMSystemSwitchExtensionPortFeature** cmdlet gets the port-level features supported by virtual switch extensions on one or more Hyper-V hosts.
The returned feature object will contain default values for the feature.
The object can be used to apply the configuration on specific ports using the Add-VmSwitchExtensionPortFeature command.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMSystemSwitchExtensionPortFeature
```

Gets all port-level features, supported by various virtual switch extensions installed on the system, that can be configured on a virtual network adapter on Hyper-V.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which the available port-level features are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

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

### -ExtensionName
Specifies one or more extension names for which the features are to be retrieved.

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
Specifies the unique identifier of the feature to be retrieved.

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
Specifies the name of the feature to be retrieved.

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

### -SystemSwitchExtension
Specifies one or more system extensions for which the features are to be retrieved.

```yaml
Type: VMSystemSwitchExtension[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS



