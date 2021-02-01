---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Update-O365AccountName
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 2E58562C-9D16-4092-91F6-3139E96A2318
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Update-O365AccountName

## SYNOPSIS
Updates the email name for an office_365_2 user account.

## SYNTAX

```
Update-O365AccountName [-LocalAccountName] <String> [-NewEmailName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Update-O365AccountName** cmdlet updates the email name for an office_365_1 user account.
The name of an office_365_2 user account is also called a Microsoft online service ID.

## EXAMPLES

### Example 1: Update the email name for a user account
```
PS C:\> Update-O365AccountName -LocalAccountName "PattiFuller" -NewEmailName "Patti@Contoso.com"
```

This command updates the email name of the office_365_2 account that is assigned to the local user account named PattiFuller.

### 1:
```
PS C:\>
```

## PARAMETERS

### -LocalAccountName
Specifies the name of a local Active Directory user account.
The cmdlet updates the email name for the office365_sbp_3 user account that is assigned to the local user name that you specify.

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

### -NewEmailName
Specifies the new email name for the office365_sbp_3 user account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-O365User](./Get-O365User.md)

