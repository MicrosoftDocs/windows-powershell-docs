---
author: Kateyanne
description: 
external help file: Microsoft.WindowsAuthenticationProtocols.Commands.dll-Help.xml
manager: jasgro
Module Name: TLS
ms.author: v-kaunu
ms.date: 10/29/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/tls/disable-tlssessionticketkey?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-TlsSessionTicketKey
---

# Disable-TlsSessionTicketKey

## SYNOPSIS
Disables a TLS session ticket key.

## SYNTAX

```
Disable-TlsSessionTicketKey [-ServiceAccountName] <NTAccount> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-TlsSessionTicketKey** cmdlet disables an administrator managed Transport Layer Security (TLS) session ticket key for the service account.
The cmdlet disables the key for the TLS session by deleting the key and the corresponding rule that uses the key.

When you disable a TLS session ticket key for the service account, the service account cannot decrypt existing TLS session tickets.
Disabling the TLS session ticket key can affect the performance of the TLS server.
The TLS server cannot create new session tickets and must negotiate session information between the client and the server every time the client connects to the TLS server.

TLS creates a session ticket by using the Transport Layer Security (TLS) Session Resumption without Server-Side State mechanism \[RFC 5077\].
This mechanism helps to improve the performance of TLS.
The TLS server uses this mechanism to create a key to encrypt a session ticket.
The client can later use the encrypted session ticket to resume communication with the TLS server.
Otherwise, the client must restart the communication by acquiring a new session ticket.
For more information, see RFC 5077, "Transport Layer Security (TLS) Session Resumption without Server-Side State."

## EXAMPLES

### Example 1: Disable a TLS session ticket key.
```
PS C:\> Disable-TlsSessionTicketKey -ServiceAccountName "Networkservice"
```

This command disables the TLS session ticket key for the service account named Networkservice.

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

### -ServiceAccountName
Specifies the name of a service account.
The cmdlet disables the TLS session ticket key for the service account.

```yaml
Type: NTAccount
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

[Export-TlsSessionTicketKey](./Export-TlsSessionTicketKey.md)

