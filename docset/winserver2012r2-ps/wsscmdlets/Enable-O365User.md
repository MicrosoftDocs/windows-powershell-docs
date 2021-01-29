---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Enable-O365User
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 98DA3D1E-3501-4732-91DC-4C4E8A04E468
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Enable-O365User

## SYNOPSIS
Enables an office_365_2 account that is assigned to a local network user account.

## SYNTAX

```
Enable-O365User [-LocalAccountName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Enable-O365User** cmdlet enables an office_365_1 account that is assigned to a local network user account.

## EXAMPLES

### Example 1: Enable an office_365_2 accountoffice_365_2
```
PS C:\> Enable-O365User -LocalAccountName "PattiFuller"
The Office 365 account is enabled.
```

This command enables an office_365_2 account that is assigned to the local user account named PattiFuller.

### 1:
```
PS C:\>
```

## PARAMETERS

### -LocalAccountName
Specifies the name of a local Active Directory user account.
The cmdlet enables the office_365_2 account that is assigned to the local user account that you specify.

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

[Disable-O365User](./Disable-O365User.md)

[Remove-O365User](./Remove-O365User.md)

