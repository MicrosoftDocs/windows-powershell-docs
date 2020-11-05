---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
keywords: powershell, cmdlet
ms.assetid: 05723256-0DD7-41F3-94BC-B9A8475F5B06
manager: dansimp
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-IISSharedConfig
ms.author: v-kaunu
ms.reviewer:
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
PS C:\> Get-IISSharedConfig
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

