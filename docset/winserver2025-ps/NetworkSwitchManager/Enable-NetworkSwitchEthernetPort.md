---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetworkSwitchEthernetPort.psm1-help.xml
Module Name: NetworkSwitchManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkswitchmanager/enable-networkswitchethernetport?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-NetworkSwitchEthernetPort
---

# Enable-NetworkSwitchEthernetPort

## SYNOPSIS
Enables an Ethernet port on a network switch.

## SYNTAX

### DeviceIdSet
```
Enable-NetworkSwitchEthernetPort -CimSession <CimSession> -DeviceID <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### PortNumberSet
```
Enable-NetworkSwitchEthernetPort -CimSession <CimSession> -PortNumber <Int32> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObjectSet
```
Enable-NetworkSwitchEthernetPort -CimSession <CimSession> -InputObject <CimInstance[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Enable-NetworkSwitchEthernetPort** cmdlet enables an Ethernet port on a network switch.

## EXAMPLES

### Example 1: Enable a port by using a device ID
```
PS C:\>$Session = New-CimSession -ComputerName "NetworkSwitch08"
PS C:\> Enable-NetworkSwitchEthernetPort -DeviceID "Ethernet17" -CimSession $Session
```

The first command creates a **CimSession** for a network switch, and then stores it in the **$Session** variable.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

The second command enables ports for the device that has the ID Ethernet17 by using the **$Session** object.

### Example 2: Enable a port by using a port number
```
PS C:\>Enable-NetworkSwitchEthernetPort -Port 21 -CimSession $Session
```

This command enables port 21.
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

### -DeviceID
Specifies a device ID.
This cmdlet enables a port on a device that this parameter specifies.

```yaml
Type: String
Parameter Sets: DeviceIdSet
Aliases:

Required: True
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
Specifies a port to enable.

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
You can pipe an array of **CimInstance** objects that correspond to Ethernet ports to this cmdlet.

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[Disable-NetworkSwitchEthernetPort](./Disable-NetworkSwitchEthernetPort.md)

[Get-NetworkSwitchEthernetPort](./Get-NetworkSwitchEthernetPort.md)

