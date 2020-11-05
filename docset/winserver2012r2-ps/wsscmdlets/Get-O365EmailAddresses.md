---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-O365EmailAddresses
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 44D63EA5-59C4-4B49-B8C3-75DC6284F013
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-O365EmailAddresses

## SYNOPSIS
Gets subscription information for the office_365_2 Integration Module.

## SYNTAX

```
Get-O365EmailAddresses [-LocalAccountName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-O365EmailAddresses** cmdlet gets subscription information of a user for the office_365_1 Integration Module.

## EXAMPLES

### Example 1: Get subscription information for a user
```
PS C:\> Get-O365EmailAddresses -LocalAccountName "PattiFuller"
```

This command gets subscription information for the user account named PattiFuller for the Office 365 Integration Module.

### 1:
```
PS C:\>
```

## PARAMETERS

### -LocalAccountName
Specifies the name of a local Active Directory user account.
The cmdlet gets subscription information for the local user that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
LocalAccountName
Type: System.String
Description: local user name

## OUTPUTS

### System.Collections.Generic.List<System.String>
This cmdlet returns a list of email addresses for a user.

## NOTES

## RELATED LINKS

[Set-O365EmailAddresses](./Set-O365EmailAddresses.md)

