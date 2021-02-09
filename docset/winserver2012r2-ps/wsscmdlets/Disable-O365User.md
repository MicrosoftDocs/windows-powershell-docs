---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Disable-O365User
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: FEBF208E-FB2C-4A70-B6D0-754D419C080C
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Disable-O365User

## SYNOPSIS
Disables an office_365_2 account that is assigned to a local network user account.

## SYNTAX

```
Disable-O365User [-LocalAccountName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Disable-O365User** cmdlet disables the office_365_1 account that is assigned to a local user account.

## EXAMPLES

### Example 1: Disable an office_365_2 accountoffice_365_2
```
PS C:\> Disable-O365User -LocalAccountName "PattiFuller"
The Office 365 account is now disabled.
```

This command disables the office_365_2 account that is assigned to the network user account named PattiFuller.

### 1:
```
PS C:\>
```

## PARAMETERS

### -LocalAccountName
Specifies the name of a local Active Directory user account.
The cmdlet disables the office_365_1 account that is assigned to the local user account that you specify.

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

### System.String
LocalAccountName
Type: System.String
Description: local user name

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-O365User](./Get-O365User.md)

[Add-O365User](./Add-O365User.md)

[Enable-O365User](./Enable-O365User.md)

[Remove-O365User](./Remove-O365User.md)

