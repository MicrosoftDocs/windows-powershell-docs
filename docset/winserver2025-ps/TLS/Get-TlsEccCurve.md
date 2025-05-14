---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.WindowsAuthenticationProtocols.Commands.dll-Help.xml
Module Name: TLS
ms.date: 05/09/2017
online version: https://learn.microsoft.com/powershell/module/tls/get-tlsecccurve?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TlsEccCurve
---
# Get-TlsEccCurve

## SYNOPSIS
Gets the list of Elliptic Curve Cryptography (ECC) cipher suites available for TLS for a computer.

## SYNTAX

```
Get-TlsEccCurve [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION

Gets the list of Elliptic Curve Cryptography (ECC) cipher suites available for TLS for a computer.

## EXAMPLES

### Example 1: Get all ECC curves

```powershell
Get-TlsEccCurve
```

```output
curve25519
NistP256
NistP384
```

This command gets all ECC curves for the computer.

### Example 2: Get the ECC curves that match a string

```powershell
Get-TlsEccCurve -Name 'Nist'
```

```output
NistP256
NistP384
```

This command gets all the ECC curves that have names that contain the string 'Nist'
(case-sensitive).

## PARAMETERS

### -Name

Specifies the name of the ECC curve to get. The cmdlet gets ECC curves that match the string that
this cmdlet specifies, so you can specify a partial name. This parameter is case-sensitive.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: None

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

[Enable-TlsEccCurve](./Enable-TlsEccCurve.md)

[Disable-TlsEccCurve](./Disable-TlsEccCurve.md)
