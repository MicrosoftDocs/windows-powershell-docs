---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Disable-HostedEmailAccount
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 1A9BC1CB-48E2-432B-B6F7-8BBC03546C7B
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Disable-HostedEmailAccount

## SYNOPSIS
Disables the hosted email account assigned to a local user account.

## SYNTAX

```
Disable-HostedEmailAccount [-LocalAccountName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Disable-HostedEmailAccount** cmdlet disables a hosted email account that is assigned to a local user account.
A hosted email service provides a hosted email account.

## EXAMPLES

### Example 1: Disable a hosted email account
```
PS C:\> Disable-HostedEmailAccount -LocalAccountName "PattiFuller"
```

This command disables the hosted email account that is assigned to the local user account named PattiFuller.

### 1:
```
PS C:\>
```

## PARAMETERS

### -LocalAccountName
Specifies the name of a local Active Directory user account.
The cmdlet disables the hosted email account that is assigned to the local user account that you specify.

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

[Add-HostedEmailAccount](./Add-HostedEmailAccount.md)

[Set-HostedEmailAccount](./Set-HostedEmailAccount.md)

[Enable-HostedEmailAccount](./Enable-HostedEmailAccount.md)

[Remove-HostedEmailAccount](./Remove-HostedEmailAccount.md)

[Clear-AssignedHostedEmailAccount](./Clear-AssignedHostedEmailAccount.md)

