---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Remove-O365Domain
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: A6800E10-0933-41A3-B6E6-F16B322A3E1C
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-O365Domain

## SYNOPSIS
Removes the current Internet domain.

## SYNTAX

```
Remove-O365Domain [<CommonParameters>]
```

## DESCRIPTION
The **Remove-O365Domain** cmdlet removes the current Internet domain for office_365_1.
You cannot remove the domain name that you are given when you sign up for office_365_2.
You can remove only custom domains that you add to office_365_2.

## EXAMPLES

### Example 1: Remove the current Internet domain
```
PS C:\> Remove-O365Domain
```

This command removes the current Internet domain.

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

[Set-O365Domain](./Set-O365Domain.md)

[Get-O365DomainConfiguration](./Get-O365DomainConfiguration.md)

