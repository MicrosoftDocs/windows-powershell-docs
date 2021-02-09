---
external help file: Wssg.Setup.Commands.dll-Help.xml
online version: 
schema: 2.0.0
title: Test-WssPrecheckResult
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 0125F46A-FB88-441F-A114-FD14388FD4EB
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Test-WssPrecheckResult

## SYNOPSIS
Verifies prerequisites for configuration of Windows Server Essentials.

## SYNTAX

```
Test-WssPrecheckResult [<CommonParameters>]
```

## DESCRIPTION
The **Test-WssPrecheckResult** cmdlet verifies prerequisites for configuration of Windows Server Essentials.
For example, if a certification authority (CA) is already installed on the server, it fails verification.

## EXAMPLES

### Example 1: Verify prerequisites for the product
```
PS C:\> Test-WssPrecheckResult
```

This command verifies prerequisites for configuration of Windows Server Essentials.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.Setup.ICCommon.PrecheckInfo
This cmdlet generates an object that represents the result of the prerequisite check.

## NOTES

## RELATED LINKS

[Test-WssConfigurationOption](./Test-WssConfigurationOption.md)

[Start-WssConfigurationService](./Start-WssConfigurationService.md)

[Get-WssConfigurationStatus](./Get-WssConfigurationStatus.md)

