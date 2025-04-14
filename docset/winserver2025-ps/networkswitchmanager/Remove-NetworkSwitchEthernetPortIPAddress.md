---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetworkSwitchEthernetPort.psm1-help.xml
Module Name: NetworkSwitchManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkswitchmanager/remove-networkswitchethernetportipaddress?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-NetworkSwitchEthernetPortIPAddress
---

# Remove-NetworkSwitchEthernetPortIPAddress

## SYNOPSIS
Removes an IP address from a port of a network switch.

## SYNTAX

### PortNumberSet
```
Remove-NetworkSwitchEthernetPortIPAddress -CimSession <CimSession> -PortNumber <Int32> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObjectSet
```
Remove-NetworkSwitchEthernetPortIPAddress -CimSession <CimSession> -InputObject <CimInstance[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-NetworkSwitchEthernetPortIPAddress** cmdlet removes an assigned IP address from a port of a network switch.

## EXAMPLES

### Example 1: Remove an IP address from a port by using the pipeline
```
PS C:\>$Session = New-CimSession -ComputerName "NetworkSwitch08"
PS C:\> Remove-NetworkSwitchEthernetPortIPAddress -CimSession $Session -PortNumber 21
```

The first command creates a **CimSession** for a network switch, and then stores it in the **$Session** variable.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

The second command removes the IP address of port 21 by using the **$Session** object.

## PARAMETERS

### -CimSession
Specifies the **CimSession** to connect to the network switch.
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

### -PortNumber
Specifies the number of a port.
This cmdlet removes the IP address from the port that this parameter specifies.

```yaml
Type: Int32
Parameter Sets: PortNumberSet
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

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Set-NetworkSwitchEthernetPortIPAddress](./Set-NetworkSwitchEthernetPortIPAddress.md)

[Get-NetworkSwitchEthernetPort](./Get-NetworkSwitchEthernetPort.md)

