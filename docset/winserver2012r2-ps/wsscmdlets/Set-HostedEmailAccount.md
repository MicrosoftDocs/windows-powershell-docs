---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Set-HostedEmailAccount
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 1844324C-1177-45C5-9EFA-E06C8A578B17
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-HostedEmailAccount

## SYNOPSIS
Assigns a hosted email account to a network user account.

## SYNTAX

```
Set-HostedEmailAccount [-LocalAccountName] <String> [-EmailAccount] <EmailAccountInfo> [<CommonParameters>]
```

## DESCRIPTION
The **Set-HostedEmailAccount** cmdlet assigns a hosted email account to a local user account.
A hosted email service provides a hosted email account.

## EXAMPLES

### Example 1: Assign a hosted email account to a local user account
```
PS C:\> Set-HostedEmailAccount -LocalAccountName "PattiFuller" -EmailAccount "PattiFuller@Constoso.com"
```

This command assigns the hosted email account named PattiFuller@Constoso.com to the local user account named PattiFuller.

## PARAMETERS

### -EmailAccount
Specifies the email account information that the hosted email service provides.

```yaml
Type: EmailAccountInfo
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LocalAccountName
Specifies the name of a local Active Directory user account.
The cmdlet assigns the hosted email account to the local user account that you specify.

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

### Microsoft.WindowsServerSolutions.HostedEmail.EmailAccountInfo
EmailAccount
Type: Microsoft.WindowsServerSolutions.HostedEmail.EmailAccountInfo
Description: email account information
AccountId Property System.String
AdditionalEmailAddresses Property System.Collections.Generic.IList<System.String>
DisplayNameProperty System.String
Enabled Property System.Boolean
ExtendedProperties Property System.Collections.Generic.IDictionary<System.String,System.String>
FirstName Property System.String
LastName Property System.String
PrimaryEmailAddress Property System.String

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-HostedEmailAccount](./Get-HostedEmailAccount.md)

[Add-HostedEmailAccount](./Add-HostedEmailAccount.md)

[Enable-HostedEmailAccount](./Enable-HostedEmailAccount.md)

[Disable-HostedEmailAccount](./Disable-HostedEmailAccount.md)

[Remove-HostedEmailAccount](./Remove-HostedEmailAccount.md)

[Clear-AssignedHostedEmailAccount](./Clear-AssignedHostedEmailAccount.md)

