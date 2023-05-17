---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.WindowsAuthenticationProtocols.Commands.dll-Help.xml
Module Name: TLS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/tls/enable-tlssessionticketkey?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-TlsSessionTicketKey
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

The `Enable-TlsSessionTicketKey` cmdlet configures a Transport Layer Security (TLS) server with an
administrator-managed TLS session ticket key, created with New-TlsSessionTicketKey, and configures
the rule that uses the key for the application service account. For example, Internet Information
Services (IIS) runs under System account so the __ServiceAccountName_ parameter should be System.

TLS creates a session ticket by using the TLS Session Resumption without Server-Side State mechanism.
For more information, see New-TlsSessionTicketKey or type `Get-Help New-TlsSessionTicketKey`.

## EXAMPLES

### Example 1: Configure a TLS server with a TLS session ticket key for the NetworkService account

```powershell
$Password = Read-Host -AsSecureString
Enable-TlsSessionTicketKey -Password $Password -Path 'C:\KeyConfig\TlsSessionTicketKey.config' -ServiceAccountName NetworkService
```

The second command configures the session ticket key for the TLS server. The command specifies the
path for the configuration file on the TLS server, and specifies that the TLS session use the
password stored in `$Password` to access the configuration file and configure the key for the
specified service account.

### Example 2: Configure a TLS server with a TLS session ticket key for System account

```powershell
$Password = Read-Host -AsSecureString
Enable-TlsSessionTicketKey -Password $Password -Path 'C:\KeyConfig\TlsSessionTicketKey.config' -ServiceAccountName System
```

The second command configures the session ticket key for the TLS server. The command specifies the
path for the configuration file on the TLS server, and specifies that the TLS session use the
password stored in `$Password` to access the configuration file and configure the key for the
specified service account.

## PARAMETERS

### -Force

Forces the command to run without asking for user confirmation.

If you specify this parameter, the cmdlet overwrites the existing session ticket key and
configuration.

```yaml
Type: System.Management.Automation.SwitchParameter
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
Type: System.Security.SecureString
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
Type: System.String
Parameter Sets: (All)
Aliases: FullName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceAccountName

Specifies the name of a service account.
The cmdlet configures the TLS session ticket key for the service account.
Only System, LocalService, NetworkService, and SID of virtual accounts are supported.

```yaml
Type: System.Security.Principal.NTAccount
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

[New-TlsSessionTicketKey](./New-TlsSessionTicketKey.md)

[Export-TlsSessionTicketKey](./Export-TlsSessionTicketKey.md)

[Disable-TlsSessionTicketKey](./Disable-TlsSessionTicketKey.md)
