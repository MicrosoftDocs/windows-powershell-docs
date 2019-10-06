---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetworkSwitchEthernetPort-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Disable-NetworkSwitchEthernetPort
ms.reviewer:
ms.assetid: 493748F1-A9D7-4FEE-A853-CDAB9A89636E
---

# Disable-NetworkSwitchEthernetPort

## SYNOPSIS
Disables an Ethernet port on a network switch.

## SYNTAX

### DeviceIdSet
```
Disable-NetworkSwitchEthernetPort -CimSession <CimSession> -DeviceID <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### PortNumberSet
```
Disable-NetworkSwitchEthernetPort -CimSession <CimSession> -PortNumber <Int32> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObjectSet
```
Disable-NetworkSwitchEthernetPort -CimSession <CimSession> -InputObject <CimInstance[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Disable-NetworkSwitchEthernetPort** cmdlet disables an Ethernet port on a network switch.

## EXAMPLES

### Example 1: Disable a port
```
PS C:\>$Session = New-CimSession -ComputerName "NetworkSwitch08"
PS C:\> Disable-NetworkSwitchEthernetPort -CimSession $Session -PortNumber 21
```

The first command creates a **CimSession** for a network switch, and then stores it in the **$Session** variable.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

This command disables port 21 for NetworkSwitch08 by using the **$Session** object.

### Example 2: Disable a port by using a device ID
```
PS C:\>Disable-NetworkSwitchEthernetPort -CimSession $Session -DeviceId "Ethernet17"
```

This command disables an Ethernet port with device ID Ethernet17 on a network switch.
The command uses a **CimSession**, similar to the first example.

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
This cmdlet disables a port on a device that this parameter specifies.

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
Specifies a port to disable.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### CimInstance[]
You can pipe an array of **CimInstance** objects that correspond to an Ethernet port to this cmdlet.

## OUTPUTS

### None
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Enable-NetworkSwitchEthernetPort](./Enable-NetworkSwitchEthernetPort.md)

[Get-NetworkSwitchEthernetPort](./Get-NetworkSwitchEthernetPort.md)

