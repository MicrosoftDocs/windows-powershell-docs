---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Disable-HostedEmailIntegration
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 4261B53C-F30A-4870-A02A-84232C5850B2
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Disable-HostedEmailIntegration

## SYNOPSIS
Disables the hosted email integration module.

## SYNTAX

```
Disable-HostedEmailIntegration [<CommonParameters>]
```

## DESCRIPTION
The **Disable-HostedEmailIntegration** cmdlet disables hosted email integration with the current third-party hosted email service.
After you disable the hosted email integration module, you can uninstall the add-in for the hosted email service by using the Uninstall-WssAddin cmdlet.

## EXAMPLES

### Example 1: Disable a hosted email integration module
```
PS C:\> Disable-HostedEmailIntegration
```

This command disables hosted email integration with the current third-party hosted email service.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-HostedEmailIntegration](./Enable-HostedEmailIntegration.md)

