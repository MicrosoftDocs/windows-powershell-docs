---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Clear-AssignedHostedEmailAccount
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: A63F86EC-E9AE-4707-B839-95501A10CA54
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Clear-AssignedHostedEmailAccount

## SYNOPSIS
Removes the relationship between a hosted email account and a local user account.

## SYNTAX

```
Clear-AssignedHostedEmailAccount [-LocalAccountName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Clear-AssignedHostedEmailAccount** cmdlet removes the relationship between a hosted email account and the local user account to which the hosted email account is assigned.
A hosted email service provides a hosted email account.

## EXAMPLES

### Example 1: Remove the relationship between a hosted email account and a local user account
```
PS C:\> Clear-AssignedHostedEmailAccount -LocalAccountName "PattiFuller"
```

This command removes the relationship between the hosted email account and the local user account named PattiFuller.

### 1:
```
PS C:\>
```

## PARAMETERS

### -LocalAccountName
Specifies the name of a local Active Directory user account.
The cmdlet removes the relationship between the hosted email account and the local user account that you specify.

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

## NOTES

## RELATED LINKS

[Get-HostedEmailAccount](./Get-HostedEmailAccount.md)

