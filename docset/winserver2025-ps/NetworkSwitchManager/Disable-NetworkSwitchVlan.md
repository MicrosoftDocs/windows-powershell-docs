---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetworkSwitchVlan.psm1-help.xml
Module Name: NetworkSwitchManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkswitchmanager/disable-networkswitchvlan?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-NetworkSwitchVlan
---

# Disable-NetworkSwitchVlan

## SYNOPSIS
Disables a VLAN of a network switch.

## SYNTAX

### InstanceIdSet
```
Disable-NetworkSwitchVlan -CimSession <CimSession> -InstanceId <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### NameSet
```
Disable-NetworkSwitchVlan -CimSession <CimSession> -Name <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VlanIdSet
```
Disable-NetworkSwitchVlan -CimSession <CimSession> -VlanID <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-NetworkSwitchVlan** cmdlet disables a virtual local area network (VLAN) of a network switch.

## EXAMPLES

### Example 1: Disable a VLAN by using an instance ID
```
PS C:\>$Session = New-CimSession -ComputerName "NetworkSwitch08"
PS C:\> Disable-NetworkSwitchVlan -InstanceID "Vlan02" -CimSession $Session
```

The first command creates a **CimSession** for a network switch, and then stores it in the **$Session** variable.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

The second command disables the VLAN that has the instance ID Vlan02 for the switch NetworkSwitch08 by using the **$Session** object.

### Example 2: Disable a VLAN by using a name
```
PS C:\>Disable-NetworkSwitchVlan -CimSession $Session -Name "VLAN22"
```

This command disables the VLAN named VLAN22.
The command includes a **CimSession**, similar to the first example.

### Example 3: Disable a VLAN by using its ID
```
PS C:\>Disable-NetworkSwitchVlan -CimSession $Session -VlanId 74
```

This command disables the VLAN that has the VLAN ID 74.
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId
Specifies the instance ID of a VLAN to disable.

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
Specifies the name of a VLAN to disable.
This **ElementName** is a friendly name.
It is not necessarily unique.

```yaml
Type: String
Parameter Sets: NameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VlanID
Specifies VLAN ID of the VLAN to disable.

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

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

### System.Object

## NOTES

## RELATED LINKS

[Enable-NetworkSwitchVlan](./Enable-NetworkSwitchVlan.md)

[Get-NetworkSwitchVlan](./Get-NetworkSwitchVlan.md)

[New-NetworkSwitchVlan](./New-NetworkSwitchVlan.md)

[Remove-NetworkSwitchVlan](./Remove-NetworkSwitchVlan.md)

[Set-NetworkSwitchVlanProperty](./Set-NetworkSwitchVlanProperty.md)

