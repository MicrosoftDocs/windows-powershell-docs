---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmsystemswitchextensionswitchfeature?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMSystemSwitchExtensionSwitchFeature

## SYNOPSIS
Gets the switch-level features on one or more Hyper-V hosts.

## SYNTAX

```
Get-VMSystemSwitchExtensionSwitchFeature [-ComputerName <String[]>] [-ExtensionName <String[]>]
 [-FeatureId <Guid[]>] [-FeatureName <String[]>] [-SystemSwitchExtension <VMSystemSwitchExtension[]>]
```

## DESCRIPTION
The **Get-VMSystemSwitchExtensionSwitchFeature** cmdlet gets the switch-level features supported by virtual switch extensions in an extension on one or more Hyper-V hosts.
The returned feature object will contain default values for the feature.
The object can be used to apply the configuration on specific ports using the Add-VMSwitchExtensionFeature cmdlet.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMSystemSwitchExtensionSwitchFeature
```

Gets all virtual switch extensions that support switch level features that can be configured on a virtual switch.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which the switch-level features in an extension are to be retrieved.
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
Specifies the name of the extension from which the switch-level features are to be retrieved.

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
Specifies the unique identifier of the features are to be retrieved.

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
Specifies the name of the switch-level features to be retrieved.

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
Specifies the extension from which the switch-level features are to be retrieved.

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



