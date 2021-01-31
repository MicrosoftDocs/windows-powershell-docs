---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Disable-ExchangeIntegration
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 2F3DE7FE-52D0-4406-ADC6-A135E565D9CC
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Disable-ExchangeIntegration

## SYNOPSIS
Disables on-premises Exchange Server Integration.

## SYNTAX

```
Disable-ExchangeIntegration [<CommonParameters>]
```

## DESCRIPTION
The **Disable-ExchangeIntegration** cmdlet disables integration of on-premises Microsoft Exchange Server Integration with the server that is running Windows Server Essentials.
Exchange Server preserves all the email accounts that you created  and all emails.
After you disable Exchange Server Integration, you can manage the email accounts and access the emails from the Exchange Management Console.

## EXAMPLES

### Example 1: Disable on-premises Exchange Server integration
```
PS C:\> Disable-ExchangeIntegration
```

This command disables integration of on-premises Exchange Server Integration.

### 1:
```
PS C:\>
```

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-ExchangeIntegration](./Enable-ExchangeIntegration.md)

