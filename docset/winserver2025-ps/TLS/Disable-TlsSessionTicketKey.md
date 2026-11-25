---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.WindowsAuthenticationProtocols.Commands.dll-Help.xml
Module Name: TLS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/tls/disable-tlssessionticketkey?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
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

The `Disable-TlsSessionTicketKey` cmdlet disables an administrator managed Transport Layer
Security (TLS) session ticket key for the service account. The cmdlet disables the key for the TLS
session by deleting the key and the corresponding rule that uses the key.

When you disable a TLS session ticket key for the service account, the service account cannot
decrypt existing TLS session tickets. Disabling the TLS session ticket key can affect the
performance of the TLS server. The TLS server cannot create new session tickets and must negotiate
session information between the client and the server every time the client connects to the TLS
server.

TLS creates a session ticket by using the TLS Session Resumption without Server-Side State mechanism.
For more information, see `New-TlsSessionTicketKey` or type `Get-Help New-TlsSessionTicketKey`.

## EXAMPLES

### Example 1: Disable a TLS session ticket key

```powershell
Disable-TlsSessionTicketKey -ServiceAccountName NetworkService
```

This command disables the TLS session ticket key for the service account named NetworkService.

## PARAMETERS

### -ServiceAccountName

Specifies the name of a service account.
The cmdlet disables the TLS session ticket key for the service account.
Only System, LocalService, NetworkService, and SID of virtual accounts are supported.

```yaml
Type: System.Security.Principal.NTAccount
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
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
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-TlsSessionTicketKey](./Enable-TlsSessionTicketKey.md)

[New-TlsSessionTicketKey](./New-TlsSessionTicketKey.md)

[Export-TlsSessionTicketKey](./Export-TlsSessionTicketKey.md)
