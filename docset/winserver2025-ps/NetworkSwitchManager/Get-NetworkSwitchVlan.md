---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetworkSwitchVlan.psm1-help.xml
Module Name: NetworkSwitchManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkswitchmanager/get-networkswitchvlan?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkSwitchVlan
---

# Get-NetworkSwitchVlan

## SYNOPSIS
Gets VLANs for a network switch.

## SYNTAX

### NameSet (Default)
```
Get-NetworkSwitchVlan -CimSession <CimSession> [-Name <String>] [<CommonParameters>]
```

### VlanIdSet
```
Get-NetworkSwitchVlan -CimSession <CimSession> -VlanId <Int32> [<CommonParameters>]
```

### InstanceIdSet
```
Get-NetworkSwitchVlan -CimSession <CimSession> -InstanceId <String> [<CommonParameters>]
```

### CaptionSet
```
Get-NetworkSwitchVlan -CimSession <CimSession> -Caption <String> [<CommonParameters>]
```

### DescriptionSet
```
Get-NetworkSwitchVlan -CimSession <CimSession> -Description <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkSwitchVlan** cmdlet gets available virtual local area networks (VLANs) for a network switch.

## EXAMPLES

### Example 1: Get all VLANs for a network switch
```
PS C:\>$Session = New-CimSession -ComputerName "NetworkSwitch08"
PS C:\> Get-NetworkSwitchVlan -CimSession $Session
Caption             Description         Name                InstanceID                       VlanID PSComputerName
-------             -----------         -----------         ----------                       ------ --------------
                    Vlan_description    default             Contoso:NetworkVL...                   1 10.19.246.18
                    Vlan_description    VLAN0002            Contoso:NetworkVL...                   2 10.19.246.18
```

The first command creates a **CimSession** for a network switch, and then stores it in the **$Session** variable.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

The second command gets all VLAN for the switch NetworkSwitch08 by using the **$Session** object.

### Example 2: Get a VLAN by using a name
```
PS C:\>Get-NetworkSwitchVlan -CimSession $Session -Name "VLAN22"
Caption             Description         Name                InstanceID                       VlanID PSComputerName
-------             -----------         -----------         ----------                       ------ --------------
                    Vlan_description    VLAN22              Contoso:NetworkVL...                   1 10.19.236.49
```

This command gets the VLAN named VLAN22.
The command includes a **CimSession**, similar to the first example.

## PARAMETERS

### -Caption
Specifies the caption of a VLAN to get.

```yaml
Type: String
Parameter Sets: CaptionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Description
Specifies the description of a VLAN to get.

```yaml
Type: String
Parameter Sets: DescriptionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId
Specifies the instance ID of a VLAN to get.

```yaml
Type: String
Parameter Sets: InstanceIdSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a VLAN to get.
This **ElementName** is a friendly name.
It is not necessarily unique.

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

### -VlanId
Specifies the VLAN ID of the VLAN to get.

```yaml
Type: Int32
Parameter Sets: VlanIdSet
Aliases:

Required: True
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

### Microsoft.Management.Infrastructure.CimInstance#CIM_NetworkVLAN

## NOTES

## RELATED LINKS

[Disable-NetworkSwitchVlan](./Disable-NetworkSwitchVlan.md)

[Enable-NetworkSwitchVlan](./Enable-NetworkSwitchVlan.md)

[New-NetworkSwitchVlan](./New-NetworkSwitchVlan.md)

[Remove-NetworkSwitchVlan](./Remove-NetworkSwitchVlan.md)

[Set-NetworkSwitchVlanProperty](./Set-NetworkSwitchVlanProperty.md)

