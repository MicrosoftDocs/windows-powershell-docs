---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmsystemswitchextensionportfeature?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMSystemSwitchExtensionPortFeature
---

# Get-VMSystemSwitchExtensionPortFeature

## SYNOPSIS
Gets the port-level features supported by virtual switch extensions on one or more Hyper-V hosts.

## SYNTAX

```
Get-VMSystemSwitchExtensionPortFeature [-FeatureName <String[]>] [-FeatureId <Guid[]>]
 [-ExtensionName <String[]>] [-SystemSwitchExtension <VMSystemSwitchExtension[]>] [-ComputerName <String[]>]
 [<CommonParameters>]
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

