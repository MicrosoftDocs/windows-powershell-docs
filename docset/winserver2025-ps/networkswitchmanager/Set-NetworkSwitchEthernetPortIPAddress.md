---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetworkSwitchEthernetPort.psm1-help.xml
Module Name: NetworkSwitchManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkswitchmanager/set-networkswitchethernetportipaddress?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetworkSwitchEthernetPortIPAddress
---

# Set-NetworkSwitchEthernetPortIPAddress

## SYNOPSIS
Sets the IP address on a port on a network switch.

## SYNTAX

### PortNumberSet
```
Set-NetworkSwitchEthernetPortIPAddress -CimSession <CimSession> -IpAddress <String> -SubnetAddress <String>
 -PortNumber <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObjectSet
```
Set-NetworkSwitchEthernetPortIPAddress -CimSession <CimSession> -IpAddress <String> -SubnetAddress <String>
 -InputObject <CimInstance[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetworkSwitchEthernetPortIPAddress** cmdlet sets the IP address of an Ethernet port on a network switch.

## EXAMPLES

### Example 1: Assign an IP address to a port
```
PS C:\>$Session = New-CimSession -ComputerName "NetworkSwitch08"
PS C:\> Set-NetworkSwitchEthernetPortIPAddress -IpAddress "10.4.10.12" -PortNumber 21 -SubnetAddress "255.255.255.248" -CimSession $Session
```

The first command creates a **CimSession** for a network switch, and then stores it in the **$Session** variable.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

The second command assigns an IP address and subnet address to the specified port by using the **$Session** object.

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

### -IpAddress
Specifies an IP address for the Ethernet port.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PortNumber
Specifies a port number.
This cmdlet sets the IP address on the port that this parameter specifies.

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

### -SubnetAddress
Specifies a subnet mask for the IP address.

```yaml
Type: String
Parameter Sets: (All)
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
You can pipe an array of **CimInstance** objects that refer to an **EthernetPort** object.

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Remove-NetworkSwitchEthernetPortIPAddress](./Remove-NetworkSwitchEthernetPortIPAddress.md)

[Get-NetworkSwitchEthernetPort](./Get-NetworkSwitchEthernetPort.md)

