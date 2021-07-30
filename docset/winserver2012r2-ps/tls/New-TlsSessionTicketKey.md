---
external help file: Microsoft.WindowsAuthenticationProtocols.Commands.dll-Help.xml
Module Name: TLS
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/tls/new-tlssessionticketkey?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-TlsSessionTicketKey
---

# New-TlsSessionTicketKey

## SYNOPSIS
Creates a TLS session ticket key configuration file.

## SYNTAX

```
New-TlsSessionTicketKey [[-Path] <String>] [-Password] <SecureString> [<CommonParameters>]
```

## DESCRIPTION
The **New-TlsSessionTicketKey** cmdlet creates a password protected Transport Layer Security (TLS) Session Ticket key configuration file.

TLS creates a session ticket by using the Transport Layer Security (TLS) Session Resumption without Server-Side State mechanism \[RFC 5077\].
This mechanism helps to improve the performance of TLS.
The TLS server uses this mechanism to create a key to encrypt a session ticket.
The client can later use the encrypted session ticket to resume communication with the TLS server.
Otherwise, the client must restart the communication by acquiring of new session ticket.
For more information, see RFC 5077, "Transport Layer Security (TLS) Session Resumption without Server-Side State."

## EXAMPLES

### Example 1: Create a TLS session ticket key
```
PS C:\> $Password = read-host -assecurestring
PS C:\> New-TlsSessionTicketKey -Path "C:\keyconfig\tlssessionticketKey.config" -Password $Password
```

This example exports the key for a TLS session ticket for a service account.

The first command prompts the user to enter a password.
The command masks the password that the user types at the prompt.
The command stores the password in the **$Password** variable

The second command creates the session ticket key configuration file for the service account named Networkservice.
The command specifies the path for the output configuration file on the TLS server, and specifies that the TLS session use the password stored in **$Password** to access the configuration file.

## PARAMETERS

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
The cmdlet outputs the generated configuration file to this path.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-TlsSessionTicketKey](./Enable-TlsSessionTicketKey.md)

[Export-TlsSessionTicketKey](./Export-TlsSessionTicketKey.md)

[Disable-TlsSessionTicketKey](./Disable-TlsSessionTicketKey.md)

