---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetworkSwitchFeature.psm1-help.xml
Module Name: NetworkSwitchManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkswitchmanager/get-networkswitchfeature?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkSwitchFeature
---

# Get-NetworkSwitchFeature

## SYNOPSIS
Gets features of a network switch.

## SYNTAX

### NameSet (Default)
```
Get-NetworkSwitchFeature -CimSession <CimSession> [-Name <String>] [<CommonParameters>]
```

### EnabledSet
```
Get-NetworkSwitchFeature -CimSession <CimSession> [-Enabled] [<CommonParameters>]
```

### DisabledSet
```
Get-NetworkSwitchFeature -CimSession <CimSession> [-Disabled] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkSwitchFeature** cmdlet gets features of a network switch.

## EXAMPLES

### Example 1: Get all features
```
PS C:\>$Session = New-CimSession -ComputerName "NetworkSwitch08"
PS C:\> Get-NetworkSwitchFeature -CimSession $Session
Name                                IsEnabled InstanceID             PSComputerName
----                                --------- ----------             --------------
SSH                                      True Contoso:Feature:2       10.19.26.49
Tacacs                                   True Contoso:Feature:3       10.19.26.49
BGP                                     False Contoso:Feature:4       10.19.26.49
VLAN                                     True Contoso:Feature:5       10.19.26.49
LACP                                     True Contoso:Feature:6       10.19.26.49
DHCP                                    False Contoso:Feature:7       10.19.26.49
LLDP                                     True Contoso:Feature:8       10.19.26.49
```

The first command creates a **CimSession** for a network switch, and then stores it in the **$Session** variable.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

The second command gets the features for the switch NetworkSwitch08 by using the **$Session** object.
This example shows representative results.

### Example 2: Get all enabled features
```
PS C:\>Get-NetworkSwitchFeature -CimSession $Session -Enabled
```

This command gets all the enabled features on a network switch.
The command includes a **CimSession**, similar to the first example.

### Example 3: Get all disabled features
```
PS C:\>Get-NetworkSwitchFeature -CimSession $Session -Disabled
```

This command gets all the disabled features on a network switch.
The command includes a **CimSession**, similar to the first example.

### Example 4: Get features by using a name
```
PS C:\>Get-NetworkSwitchFeature -CimSession $Session -FeatureName "*BGP*"
```

This command gets all features that contain the string BGP on a network switch.
The command includes a **CimSession**, similar to the first example.

## PARAMETERS

### -CimSession
Specifies the **CimSession** that this cmdlet uses to connect to the network switch.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Disabled
Indicates that this cmdlet gets only disabled features.

```yaml
Type: SwitchParameter
Parameter Sets: DisabledSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enabled
Indicates that this cmdlet gets only enabled features.

```yaml
Type: SwitchParameter
Parameter Sets: EnabledSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a feature to get.
Use wildcard characters to specify multiple features.

```yaml
Type: String
Parameter Sets: NameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#MSFT_Feature

## NOTES

## RELATED LINKS

[Disable-NetworkSwitchFeature](./Disable-NetworkSwitchFeature.md)

[Enable-NetworkSwitchFeature](./Enable-NetworkSwitchFeature.md)

