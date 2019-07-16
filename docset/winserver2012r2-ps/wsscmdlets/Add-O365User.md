---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Add-O365User
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: E2C36892-15E2-4151-9575-3070EEDBCA04
ms.author: v-anbarr
ms.reviewer: brianlic
---

# Add-O365User

## SYNOPSIS
Creates an office_365_2 account and assigns it to a local user account.

## SYNTAX

```
Add-O365User [-LocalAccountName] <String> [-O365AccountUPN] <String> [-License <O365UserLicense[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-O365User** cmdlet creates an office_365_1 account and assigns it to a local user account.

## EXAMPLES

### Example 1: Create an office_365_2 accountoffice_365_2
```
PS C:\> Add-O365User -LocalAccountName "Admin" -O365AccountUPN "Admin@Contoso.onmicrosoft.com"
An Office 365 account was added.
```

This command creates an office_365_2 account named Admin@Contoso.onmicrosoft.com and assigns it to the local user account named Admin.

### 1:
```
PS C:\>
```

## PARAMETERS

### -License
Specifies an array of office_365_2 licenses for the account.

```yaml
Type: O365UserLicense[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalAccountName
Specifies the name of a local Active Directory user account.
The cmdlet creates an office_365_2 account and assigns it to the local user account that you specify.

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

### -O365AccountUPN
Specifies a user principal name (UPN).
The cmdlet creates an office_365_2 account that has the UPN that you specify.

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

### System.String,System.String
LocalAccountName
Type: System.String
Description: name of a local user account

O365AccountUPN
Type: System.String
Description: user principal name

## OUTPUTS

### Microsoft.WindowsServerSolutions.O365Integration.O365User
This cmdlet returns a class that represents an office_365_2 online account.
When output: office_365_2 online account exists
ObjectId Property System.Guid
UserPrincipalName Property System.String
Activated Property System.Boolean
LocalUserName Property System.String
Licenses Property System.Collections.ObjectModel.ReadOnlyCollection\<O365UserLicense\>

## NOTES

## RELATED LINKS

[Get-O365User](./Get-O365User.md)

[Enable-O365User](./Enable-O365User.md)

[Disable-O365User](./Disable-O365User.md)

[Remove-O365User](./Remove-O365User.md)

