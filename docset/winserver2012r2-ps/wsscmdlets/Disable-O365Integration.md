---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Disable-O365Integration
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 03A5B29A-9082-4100-92BC-94737C09F0BB
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Disable-O365Integration

## SYNOPSIS
Disables the office_365_2 Integration Module.

## SYNTAX

```
Disable-O365Integration [<CommonParameters>]
```

## DESCRIPTION
The **Disable-O365Integration** cmdlet disables integration between Windows Server Essentials and office_365_1.
When you disable the Office 365 Integration Module, you can no longer manage office_365_2 user accounts and licenses from the dashboard.

## EXAMPLES

### Example 1: Disable the Office 365 Integration Module
```
PS C:\> Disable-O365Integration
The Office 365 account is now disabled.
```

This command disables integration between Windows Server Essentials and office_365_2.

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

[Enable-O365Integration](./Enable-O365Integration.md)

