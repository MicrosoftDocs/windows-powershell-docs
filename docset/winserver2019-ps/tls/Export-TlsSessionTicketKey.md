---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.WindowsAuthenticationProtocols.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.assetid: E560AA28-2179-4899-B429-727D9AB17FD1
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Export-TlsSessionTicketKey
ms.reviewer:
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

TLS creates a session ticket by using the TLS Session Resumption without Server-Side State mechanism.
For more information, see New-TlsSessionTicketKey or type `Get-Help New-TlsSessionTicketKey`.

## EXAMPLES

### Example 1: Export a TLS session ticket key
```
PS C:\>$Password = Read-Host -AsSecureString
PS C:\> Export-TlsSessionTicketKey -Password $Password -Path "C:\KeyConfig\TlsSessionTicketKey.config" -ServiceAccountName "NetworkService"
```

The first command prompts the user to enter a password by using the **Read-Host** cmdlet.
The command masks the password that the user types at the prompt.
For more information, type `Get-Help Read-Host`.
The command stores the password in the **$Password** variable.

The second command exports the session ticket key for the service account named NetworkService from the configuration file on the TLS server.
The command specifies the path for the configuration file on the TLS server, and specifies that the TLS session use the password stored in **$Password** to access the configuration file.

## PARAMETERS

### -Password
Specifies the password, as a secure string, for the key.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceAccountName
Specifies the name of a service account.
The cmdlet exports the configuration of the TLS session ticket key for the service account.
Only System, LocalService, NetworkService, and SID of virtual accounts are supported.

```yaml
Type: NTAccount
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

