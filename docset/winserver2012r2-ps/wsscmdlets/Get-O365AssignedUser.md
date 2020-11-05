---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-O365AssignedUser
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 40777BFD-F7A1-4429-8166-0A37CEBA2F85
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-O365AssignedUser

## SYNOPSIS
Gets the office_365_2 account assigned to a network user account.

## SYNTAX

```
Get-O365AssignedUser [-LocalAccountName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-O365AssignedUser** cmdlet gets the office_365_1 account that is assigned to a local network user account.

## EXAMPLES

### Example 1: Get the Office 365 account assigned to a local user account
```
PS C:\> Get-O365AssignedUser -LocalAccountName "PattiFuller"
```

This command gets the office_365_2 account that is assigned to the local user account named PattiFuller.

### 1:
```
PS C:\>
```

## PARAMETERS

### -LocalAccountName
Specifies the name of a local Active Directory user account.
The cmdlet gets the office_365_2 account assigned to the local user account that you specify.

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

### Microsoft.WindowsServerSolutions.O365Integration.O365User
This cmdlet returns a class that represents office_365_2 online account.
ObjectId Property System.Guid
UserPrincipalName Property System.String
Activated Property System.Boolean
LocalUserName Property System.String
Licenses Property System.Collections.ObjectModel.ReadOnlyCollection\<O365UserLicense\>

## NOTES

## RELATED LINKS

[Set-O365AssignedUser](./Set-O365AssignedUser.md)

[Clear-O365AssignedUser](./Clear-O365AssignedUser.md)

