---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetworkSwitchVlan.psm1-help.xml
Module Name: NetworkSwitchManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkswitchmanager/new-networkswitchvlan?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetworkSwitchVlan
---

# New-NetworkSwitchVlan

## SYNOPSIS
Creates a VLAN for a network switch.

## SYNTAX

```
New-NetworkSwitchVlan [-CimSession] <CimSession> [[-Caption] <String>] [[-Description] <String>]
 [-VlanID] <Int32> [-Name] <String> [<CommonParameters>]
```

## DESCRIPTION
The **New-NetworkSwitchVlan** cmdlet creates a virtual local area network (VLAN) for a network switch.

## EXAMPLES

### Example 1: Create a VLAN
```
PS C:\>$Session = New-CimSession -ComputerName "NetworkSwitch08"
PS C:\> New-NetworkSwitchVlan -Name "Contoso07VLAN" -Caption "VLAN 07" -CimSession $Session
Caption             Description         ElementName         InstanceID                       VlanID PSComputerName
-------             -----------         -----------         ----------                       ------ --------------
VLAN 07                                 VLAN0004            Contoso:NetworkVL...                  4 10.19.26.4
```

The first command creates a **CimSession** for a network switch, and then stores it in the **$Session** variable.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

The second creates a VLAN for the switch NetworkSwitch08 by using the **$Session** object.

## PARAMETERS

### -Caption
Specifies a caption for the new VLAN.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description of the new VLAN.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name to use as the VLAN **ElementName**.
This is a friendly name.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VlanID
Specifies a VLAN ID for the new VLAN.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Disable-NetworkSwitchVlan](./Disable-NetworkSwitchVlan.md)

[Enable-NetworkSwitchVlan](./Enable-NetworkSwitchVlan.md)

[Get-NetworkSwitchVlan](./Get-NetworkSwitchVlan.md)

[Remove-NetworkSwitchVlan](./Remove-NetworkSwitchVlan.md)

[Set-NetworkSwitchVlanProperty](./Set-NetworkSwitchVlanProperty.md)

