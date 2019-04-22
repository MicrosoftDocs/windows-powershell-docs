---
external help file: Microsoft.WindowsAuthenticationProtocols.Commands.dll-Help.xml
Module Name: TLS
online version: 
schema: 2.0.0
title: Enable-TlsSessionTicketKey
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 2A91DDA4-6E64-42D8-A395-5AAFE8C757C8
ms.author: kenwith
ms.reviewer: brianlic
---

# Enable-TlsSessionTicketKey

## SYNOPSIS
Configures a TLS server with a TLS session ticket key.

## SYNTAX

```
Enable-TlsSessionTicketKey [-ServiceAccountName] <NTAccount> [-Path] <String> [-Password] <SecureString>
 [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-TlsSessionTicketKey** cmdlet configures a Transport Layer Security (TLS) server with an administrator-managed TLS session ticket key, and configures the rule that uses the key for the application service account.

TLS creates a session ticket by using the Transport Layer Security (TLS) Session Resumption without Server-Side State mechanism \[RFC 5077\].
This mechanism helps to improve the performance of TLS.
The TLS server uses this mechanism to create a key to encrypt a session ticket.
The client can later use the encrypted session ticket to resume communication with the TLS server.
Otherwise, the client must restart the communication by acquiring a new session ticket.
For more information, see RFC 5077, "Transport Layer Security (TLS) Session Resumption without Server-Side State."

## EXAMPLES

### Example 1: Configure a TLS server with a TLS session ticket key
```
PS C:\> $Password = read-host -assecurestring PS C:\>Enable-TlsSessionTicketKey -Path "C:\keyconfig\tlssessionticketKey.config" -Password $Password -ServiceAccountName "Networkservice"
```

This example configures a TLS server with a key for the TLS session ticket.

The first command prompts the user to enter a password.
The command masks the password that the user types at the prompt.
The command stores the password in the **$Password** variable

The second command configures the session ticket key for the TLS server.
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

### -Force
Forces the command to run without asking for user confirmation.

If you specify this parameter, the cmdlet overwrites the existing session ticket key and configuration.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Specifies the password, as a secure string, for the configuration file of the TLS server.

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

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceAccountName
Specifies the name of a service account.
The cmdlet configures the TLS session ticket key for the service account.

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

[New-TlsSessionTicketKey](./New-TlsSessionTicketKey.md)

[Export-TlsSessionTicketKey](./Export-TlsSessionTicketKey.md)

[Disable-TlsSessionTicketKey](./Disable-TlsSessionTicketKey.md)

