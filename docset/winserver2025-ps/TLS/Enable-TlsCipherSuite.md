---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.WindowsAuthenticationProtocols.Commands.dll-Help.xml
Module Name: TLS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/tls/enable-tlsciphersuite?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-TlsCipherSuite
---

# Enable-TlsCipherSuite

## SYNOPSIS
Enables a TLS cipher suite.

## SYNTAX

```
Enable-TlsCipherSuite [[-Position] <UInt32>] [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Enable-TlsCipherSuite` cmdlet enables a cipher suite. This cmdlet adds the cipher suite to the
list of Transport Layer Security (TLS) protocol cipher suites for the computer. If you do not
specify a position in the list, this cmdlet adds it at the lowest position. No restart is required
for changes to take effect.

If a cipher suite is not enabled for TLS based secure channel (Schannel) registry settings, then the
cipher suite is not used.

This cmdlet is based on Cryptography Next Generation (CNG) Cryptographic Configuration. Schannel
registry settings and settings specified by means of Security Support Provider Interface (SSPI) by
each app can override CNG Cryptographic Configuration. Other settings under
`HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL` can also configure
cipher suites. These settings can impact whether a cipher suite can be used. For example, disabling
of SHA hashes supported by TLS disables the corresponding cipher suites. Additionally, applications
can limit the algorithms using SSPI. For more information about TLS settings, see
[How to restrict the use of certain cryptographic algorithms and protocols in Schannel.dll](https://support.microsoft.com/kb/245030).

## EXAMPLES

### Example 1: Enable a cipher suite

```powershell
Enable-TlsCipherSuite -Name TLS_DHE_DSS_WITH_AES_256_CBC_SHA
```

This command enables cipher suite named TLS_DHE_DSS_WITH_AES_256_CBC_SHA.
This command adds the cipher suite the TLS cipher suite list as the lowest priority.

### Example 2: Enable a cipher suite as the lowest priority

```powershell
Enable-TlsCipherSuite -Name TLS_DHE_DSS_WITH_AES_256_CBC_SHA -Position 4294967295
```

This command enables cipher suite named TLS_DHE_DSS_WITH_AES_256_CBC_SHA. This command adds the
cipher suite the TLS cipher suite list as the lowest priority. Unlike the first example, this
command explicitly specifies position number 4294967295, which is the value of
CRYPT_PRIORITY_BOTTOM.

### Example 3: Enable a cipher suite as the highest priority

```powershell
Enable-TlsCipherSuite -Name TLS_DHE_DSS_WITH_AES_256_CBC_SHA -Position 0
```

This command enables cipher suite named `TLS_DHE_DSS_WITH_AES_256_CBC_SHA`. This command adds the
cipher suite the TLS cipher suite list at position 0, which is the highest priority.

## PARAMETERS

### -Name

Specifies the name of the TLS cipher suite to enable.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Position

Specifies the position at which to insert the cipher suite in the ordered list of TLS cipher suites.
The cmdlet inserts the cipher suite at the position that this parameter specifies, ahead of any
existing cipher suites.

Specify a value of 0 or CRYPT_PRIORITY_TOP to insert the function at the top of the list. Specify a
value of 4294967295 or 0xFFFFFFFF or CRYPT_PRIORITY_BOTTOM to insert the function at the end of the
list.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
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

[Disable-TlsCipherSuite](./Disable-TlsCipherSuite.md)

[Get-TlsCipherSuite](./Get-TlsCipherSuite.md)
