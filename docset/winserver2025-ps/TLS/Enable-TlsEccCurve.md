---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.WindowsAuthenticationProtocols.Commands.dll-Help.xml
Module Name: TLS
ms.date: 05/09/2017
online version: https://learn.microsoft.com/powershell/module/tls/enable-tlsecccurve?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-TlsEccCurve
---

# Enable-TlsEccCurve

## SYNOPSIS
Enables Elliptic Curve Cryptography (ECC) cipher suites available for TLS.

## SYNTAX

```
Enable-TlsEccCurve [[-Position] <UInt32>] [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Enables Elliptic Curve Cryptography (ECC) cipher suites available for TLS for a computer.

## EXAMPLES

### Example 1

```powershell
Enable-TlsEccCurve 'NistP384' -Position 0
```

This command enables Elliptic Curve Cryptography cipher suite named 'NistP384' at position 0, which
is the highest priority.

## PARAMETERS

### -Name

Specifies the name of the ECC cipher suite to enable.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Position

Specifies the position at which to insert the cipher suite in the ordered list of ECC cipher suites.
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-TlsEccCurve](./Get-TlsEccCurve.md)

[Disable-TlsEccCurve](./Disable-TlsEccCurve.md)
