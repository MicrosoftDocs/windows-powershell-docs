---
external help file: Microsoft.WindowsAuthenticationProtocols.Commands.dll-Help.xml
Module Name: TLS
online version: 
schema: 2.0.0
title: Export-TlsSessionTicketKey
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: E560AA28-2179-4899-B429-727D9AB17FD1
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Export-TlsSessionTicketKey

## SYNOPSIS
Exports a TLS session ticket key.

## SYNTAX

```
Export-TlsSessionTicketKey [-ServiceAccountName] <NTAccount> [[-Path] <String>] [-Password] <SecureString>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Export-TlsSessionTicketKey** cmdlet exports the administrator managed Transport Layer Security (TLS) session ticket key for a service account.

TLS creates a session ticket by using the Transport Layer Security (TLS) Session Resumption without Server-Side State mechanism \[RFC 5077\].
This mechanism helps to improve the performance of TLS.
The TLS server uses this mechanism to create a key to encrypt a session ticket.
The client can later use the encrypted session ticket to resume communication with the TLS server.
Otherwise, the client must restart the communication by acquiring of new session ticket.
For more information, see RFC 5077, "Transport Layer Security (TLS) Session Resumption without Server-Side State."

## EXAMPLES

### Example 1: Export a TLS session ticket key
```
PS C:\> $Password = read-host -assecurestring PS C:\>Export-TlsSessionTicketKey -Path "C:\keyconfig\tlssessionticketKey.config" -Password $Password -ServiceAccountName "Networkservice"
```

This example exports the key for a TLS session ticket for a service account.

The first command prompts the user to enter a password.
The command masks the password that the user types at the prompt.
The command stores the password in the **$Password** variable.

The second command exports the session ticket key for the service account named Networkservice from the configuration file on the TLS server.
The command specifies the path for the configuration file on the TLS server, and specifies that the TLS session use the password stored in **$Password** to access the configuration file.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Specifies the password, as a secure string, for the key.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Path
Specifies the path of the configuration file for the TLS server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: FullName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceAccountName
Specifies the name of a service account.
The cmdlet exports the configuration of the TLS session ticket key for the service account.

```yaml
Type: NTAccount
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-TlsSessionTicketKey](./Enable-TlsSessionTicketKey.md)

[New-TlsSessionTicketKey](./New-TlsSessionTicketKey.md)

[Disable-TlsSessionTicketKey](./Disable-TlsSessionTicketKey.md)

