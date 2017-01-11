---
author: brianlic-msft
description: 
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-IISSharedConfig
ms.assetid: 05723256-0DD7-41F3-94BC-B9A8475F5B06
---

# Get-IISSharedConfig

## SYNOPSIS
Gets IIS shared configuration status.

## SYNTAX

```
Get-IISSharedConfig [<CommonParameters>]
```

## DESCRIPTION
The **Get-IISSharedConfig** cmdlet gets the current status of the IIS shared configuration feature.

## EXAMPLES

### Example 1: Get shared configuration status
```
PS C:\>Get-IISSharedConfig
Enabled = True
Physical Path = C:\export
UserName = administrator
```

This command gets the status of the IIS shared configuration.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-IISSharedConfig](./Disable-IISSharedConfig.md)

[Enable-IISSharedConfig](./Enable-IISSharedConfig.md)

