---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetworkSwitchConfiguration-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Restore-NetworkSwitchConfiguration
ms.reviewer:
ms.assetid: B1210FE0-9807-4690-BBA3-C0D46E0E1888
---

# Restore-NetworkSwitchConfiguration

## SYNOPSIS
Restores configuration for a network switch.

## SYNTAX

```
Restore-NetworkSwitchConfiguration [-CimSession] <CimSession> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Restore-NetworkSwitchConfiguration** cmdlet restores configuration for a network switch to the last saved startup configuration.

## EXAMPLES

### Example 1: Restore the configuration for a network switch
```
PS C:\>$Session = New-CimSession -ComputerName "NetworkSwitch08"
PS C:\> Restore-NetworkSwitchConfiguration -CimSession $Session
```

The first command creates a **CimSession** for a network switch, and then stores it in the **$Session** variable.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

The second command restores the configuration from the last saved configuration for NetworkSwitch08 by using the **$Session** object.

## PARAMETERS

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

### None

## OUTPUTS

### None
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Save-NetworkSwitchConfiguration](./Save-NetworkSwitchConfiguration.md)

