---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetworkSwitchEthernetPort.psm1-help.xml
Module Name: NetworkSwitchManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkswitchmanager/get-networkswitchethernetport?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkSwitchEthernetPort
---

# Get-NetworkSwitchEthernetPort

## SYNOPSIS
Gets port information for a network switch.

## SYNTAX

### DeviceIDSet (Default)
```
Get-NetworkSwitchEthernetPort -CimSession <CimSession> [-DeviceId <String>] [<CommonParameters>]
```

### FullDuplexEnabledSet
```
Get-NetworkSwitchEthernetPort -CimSession <CimSession> [-FullDuplexEnabled] [<CommonParameters>]
```

### FullDuplexDisabledSet
```
Get-NetworkSwitchEthernetPort -CimSession <CimSession> [-FullDuplexDisabled] [<CommonParameters>]
```

### PortNumberSet
```
Get-NetworkSwitchEthernetPort -CimSession <CimSession> -PortNumber <Int32> [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkSwitchEthernetPort** cmdlet gets port information for a network switch.

## EXAMPLES

### Example 1: Get all the ports for a device
```
PS C:\>$Session = New-CimSession -ComputerName "NetworkSwitch08"
PS C:\> Get-NetworkSwitchEthernetPort -CimSession $Session
```

The first command creates a **CimSession** for a network switch, and then stores it in the **$Session** variable.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

The second command gets the ports for NetworkSwitch08 by using the **$Session** object.

### Example 2: Get a specific port
```
PS C:\>Get-NetworkSwitchEthernetPort -PortNumber 21 -CimSession $Session
Name            PortNumber DeviceID       FullDuplex    AutoSense     PortType  MaxDataSize
----            ---------- --------       ----------    ---------     --------  -----------
Ethernet17              21 Ethernet17           True        False            0         9214
```

This command gets port 21.
The example shows the console output for the command.
The command includes a **CimSession**, similar to the first example.

### Example 3: Get a port with a specified ID
```
PS C:\>Get-NetworkSwitchEthernetPort -DeviceID "Ethernet17" -CimSession $Session
```

This command gets the port for the device that has the ID Ethernet17.
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

### -DeviceId
Specifies a device ID.
This cmdlet gets information for the port that this parameter specifies.

```yaml
Type: String
Parameter Sets: DeviceIDSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullDuplexDisabled
Indicates that this cmdlet returns only ports that have **FullDuplex** disabled.

```yaml
Type: SwitchParameter
Parameter Sets: FullDuplexDisabledSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullDuplexEnabled
Indicates that this cmdlet returns only ports that have **FullDuplex** enabled.

```yaml
Type: SwitchParameter
Parameter Sets: FullDuplexEnabledSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PortNumber
Specifies a port number.
This cmdlet gets the port that the parameter specifies.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#CIM_EthernetPort

## NOTES

## RELATED LINKS

[Disable-NetworkSwitchEthernetPort](./Disable-NetworkSwitchEthernetPort.md)

[Enable-NetworkSwitchEthernetPort](./Enable-NetworkSwitchEthernetPort.md)

