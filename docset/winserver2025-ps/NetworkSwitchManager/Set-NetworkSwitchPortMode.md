---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetworkSwitchEthernetPort.psm1-help.xml
Module Name: NetworkSwitchManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkswitchmanager/set-networkswitchportmode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetworkSwitchPortMode
---

# Set-NetworkSwitchPortMode

## SYNOPSIS
Sets the port mode on a network switch.

## SYNTAX

### AccessSet
```
Set-NetworkSwitchPortMode -CimSession <CimSession> [-AccessMode] -VlanID <Int32> -InputObject <CimInstance[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RouteSet
```
Set-NetworkSwitchPortMode -CimSession <CimSession> [-RouteMode] -IpAddress <String> -SubnetAddress <String>
 -InputObject <CimInstance[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### TrunkSet
```
Set-NetworkSwitchPortMode -CimSession <CimSession> [-TrunkMode] -VlanIDs <UInt16[]>
 -InputObject <CimInstance[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetworkSwitchPortMode** cmdlet sets the port mode to access, trunk or route on a network switch.

## EXAMPLES

### Example 1: Set a port to trunk mode
```
PS C:\>$Session = New-CimSession -ComputerName "NetworkSwitch08"
PS C:\> Set-NetworkSwitchPortMode -CimSession $Session -TrunkMode -VlanIDs 2,17,22
```

The first command creates a **CimSession** for a network switch, and then stores it in the **$Session** variable.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

The second command sets NetworkSwitch08 to use trunk mode by using the **$Session** object.
The command specifies IDs for three VLANs.

### Example 2: Set a port to route mode
```
PS C:\>Set-NetworkSwitchPortMode -CimSession $Session -IpAddress "10.14.1.1" -RouteMode -SubnetAddress "255.255.0.0"
```

This command sets the port to route mode.
The command specifies its IP address and the subnet mask.
The command includes a **CimSession**, similar to the first example.

## PARAMETERS

### -AccessMode
Indicates that this cmdlet sets the port to access mode.

```yaml
Type: SwitchParameter
Parameter Sets: AccessSet
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
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IpAddress
Specifies an IP address to set for the port in route mode.

```yaml
Type: String
Parameter Sets: RouteSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouteMode
Indicates that this cmdlet sets the port to route mode.

```yaml
Type: SwitchParameter
Parameter Sets: RouteSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetAddress
Specifies the subnet mask to set for the port in route mode.

```yaml
Type: String
Parameter Sets: RouteSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrunkMode
Indicates that this cmdlet sets the port to trunk mode.

```yaml
Type: SwitchParameter
Parameter Sets: TrunkSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VlanID
Specifies the virtual local area network (VLAN) ID of the VLAN to set for the port in access mode.

```yaml
Type: Int32
Parameter Sets: AccessSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VlanIDs
Specifies the VLAN IDs of the VLANs to set for the port in trunk mode.

```yaml
Type: UInt16[]
Parameter Sets: TrunkSet
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
You can pipe an array of **CimInstance** objects that correspond to a network switch port to this cmdlet.

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-NetworkSwitchEthernetPort](./Get-NetworkSwitchEthernetPort.md)

