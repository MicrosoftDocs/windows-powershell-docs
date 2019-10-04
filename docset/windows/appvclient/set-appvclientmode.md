---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-AppvClientMode
ms.reviewer:
ms.assetid: 83DDDF89-2EE5-41A9-9879-84434B9482B5
---

# Set-AppvClientMode

## SYNOPSIS
Sets the mode in which the client runs.

## SYNTAX

### Normal
```
Set-AppvClientMode [-Normal] [<CommonParameters>]
```

### Uninstall
```
Set-AppvClientMode [-Uninstall] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AppvClientMode** cmdlet sets the mode in which the client runs.
By default, the cmdlet is set to *Normal* and the Microsoft Application Virtualization (App-V) Client runs normally.
If the *Uninstall* parameter is specified, the App-V Client prevents all client activity from happening which includes adding and publishing packages and creating virtual environments.

## EXAMPLES


## PARAMETERS

### -Normal
Indicates that the App-V Client functions normally.
This means all adding and publishing of App-V packages and creating of Virtual environments function normally.

```yaml
Type: SwitchParameter
Parameter Sets: Normal
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Uninstall
Indicates that this cmdlet prevents the App-V Client from adding and publishing packages or creating any virtual environments.
This is set to enable an uninstall of the App-V Client to correctly occur.

```yaml
Type: SwitchParameter
Parameter Sets: Uninstall
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AppvClientMode](./Get-AppvClientMode.md)

