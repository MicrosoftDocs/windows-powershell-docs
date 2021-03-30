---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Start-SbecInstance
ms.reviewer:
ms.assetid: E066D528-8956-4F9F-931E-D4D35FE72899
---

# Start-SbecInstance

## SYNOPSIS
Starts the Setup and Boot Event Collector service.

## SYNTAX

```
Start-SbecInstance [-Service] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Start-SbecInstance** cmdlet starts the Setup and Boot Event Collector service.

You must have the Builtin Administrator privilege to run this command.

## EXAMPLES

### Example 1: Start the Boot Event Collector
```
PS C:\> Start-SbecInstance -Service
```

This command starts the Boot Event Collector service.

## PARAMETERS

### -PassThru
Returns an object representing the started service.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Service
Starts the Setup and BEC service on the current computer.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
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

### None.

## OUTPUTS

### System.ServiceProcess.ServiceController

## NOTES

## RELATED LINKS

[Get-SbecActiveConfig](./Get-SbecActiveConfig.md)

[Set-SbecActiveConfig](./Set-SbecActiveConfig.md)

[Stop-SbecInstance](./Stop-SbecInstance.md)

[Test-SbecActiveConfig](./Test-SbecActiveConfig.md)

