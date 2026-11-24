---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetworkSwitchVlan.psm1-help.xml
Module Name: NetworkSwitchManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkswitchmanager/remove-networkswitchvlan?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-NetworkSwitchVlan
---

# Remove-NetworkSwitchVlan

## SYNOPSIS
Removes network switch VLANs.

## SYNTAX

### InstanceIdSet
```
Remove-NetworkSwitchVlan -CimSession <CimSession> [-InstanceId <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### NameSet
```
Remove-NetworkSwitchVlan -CimSession <CimSession> [-Name <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VlanIdSet
```
Remove-NetworkSwitchVlan -CimSession <CimSession> [-VlanId <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObjectSet
```
Remove-NetworkSwitchVlan -CimSession <CimSession> -InputObject <CimInstance[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-NetworkSwitchVlan** cmdlet removes virtual local area networks (VLANs) from a network switch.

## EXAMPLES

### Example 1: Remove a VLAN that has a specified ID
```
PS C:\>$Session = New-CimSession -ComputerName "NetworkSwitch08"
PS C:\> Remove-NetworkSwitchVlan -CimSession $Session -VlanID 2
```

The first command creates a **CimSession** for a network switch, and then stores it in the **$Session** variable.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

The second command removes the VLAN that has a VLAN ID of 2 for the switch NetworkSwitch08 by using the **$Session** object.

### Example 2: Remove a VLAN for a specified instance ID
```
PS C:\>Remove-NetworkSwitchVlan -CimSession $Session -InstanceID "Contoso:NetworkVLAN:Vlan4"
```

This command removes the VLAN for the specified instance ID.
The command includes a **CimSession**, similar to the first example.

### Example 3: Remove VLANs that have names that contain a string
```
PS C:\>Remove-NetworkSwitchVlan -CimSession $Session -Name "*Contoso*"
```

This command removes all VLANs that have friendly names that include the string Contoso.
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

### -InstanceId
Specifies the instance ID of a VLAN to remove.

```yaml
Type: String
Parameter Sets: InstanceIdSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name for a VLAN to remove.
You can use wildcard characters to select multiple VLANs to remove.

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
Specifies the ID of a VLAN to remove.

```yaml
Type: Int32
Parameter Sets: VlanIdSet
Aliases:

Required: False
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
You can pipe an array of **CimInstance** objects that correspond to network switch VLANs to this cmdlet.

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Disable-NetworkSwitchVlan](./Disable-NetworkSwitchVlan.md)

[Enable-NetworkSwitchVlan](./Enable-NetworkSwitchVlan.md)

[Get-NetworkSwitchVlan](./Get-NetworkSwitchVlan.md)

[New-NetworkSwitchVlan](./New-NetworkSwitchVlan.md)

[Set-NetworkSwitchVlanProperty](./Set-NetworkSwitchVlanProperty.md)

