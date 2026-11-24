---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetworkSwitchVlan.psm1-help.xml
Module Name: NetworkSwitchManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkswitchmanager/set-networkswitchvlanproperty?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetworkSwitchVlanProperty
---

# Set-NetworkSwitchVlanProperty

## SYNOPSIS
Modifies properties on a VLAN on a network switch.

## SYNTAX

### VlanIdSet
```
Set-NetworkSwitchVlanProperty -CimSession <CimSession> [-Property <Hashtable>] -VlanId <Int32[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObjectSet
```
Set-NetworkSwitchVlanProperty -CimSession <CimSession> [-Property <Hashtable>] -InputObject <CimInstance[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetworkSwitchVlanProperty** cmdlet modifies settable properties on a virtual local area network (VLAN) on a network switch.

## EXAMPLES

### Example 1: Set properties for a VLAN
```
PS C:\>$Session = New-CimSession -ComputerName "NetworkSwitch08"
PS C:\> $VlanName = "Contoso VLAN 07"
PS C:\> $Description = "This VLAN is used to create a virtual Contoso company LAN"
PS C:\> Set-NetworkSwitchVlanProperty -VlanId 12 -Property @{ElementName = $VlanName; Description = $Description} -CimSession $Session
```

The first command creates a **CimSession** for a network switch, and then stores it in the **$Session** variable.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

The second and third commands assign values to the **$VlanName** variable and the **$Description** variable.
These are the values of the key/value pairs.

The final command modifies the properties of the VLAN identified by the VLAN ID 5 to include the name/value pairs specified by the **Property** parameter.
The command uses standard syntax to create a hash table that contains the name/value pairs.
The command operates on the network switch named NetworkSwitch08 by using the **$Session** object.

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

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObjectSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Property
Specifies a hash table of name/value pairs.
The cmdlet sets the properties that this parameter specifies.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VlanId
Specifies an array of VLAN IDs of VLANs to modify.

```yaml
Type: Int32[]
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

### Microsoft.Management.Infrastructure.CimInstance[]
You can pipe an array of **CimInstance** objects that represent VLANs to this cmdlet.

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Disable-NetworkSwitchVlan](./Disable-NetworkSwitchVlan.md)

[Enable-NetworkSwitchVlan](./Enable-NetworkSwitchVlan.md)

[Get-NetworkSwitchVlan](./Get-NetworkSwitchVlan.md)

[New-NetworkSwitchVlan](./New-NetworkSwitchVlan.md)

[Remove-NetworkSwitchVlan](./Remove-NetworkSwitchVlan.md)

[Set-NetworkSwitchPortProperty](./Set-NetworkSwitchPortProperty.md)

