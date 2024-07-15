---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.WindowsAuthenticationProtocols.Commands.dll-Help.xml
Module Name: TLS
ms.date: 05/09/2017
online version: https://learn.microsoft.com/powershell/module/tls/disable-tlsecccurve?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-TlsEccCurve
---

# Disable-TlsEccCurve

## SYNOPSIS
Disables the Elliptic Curve Cryptography (ECC) cipher suites available for TLS(Transport Layer
Security) for a computer.

## SYNTAX

```
Disable-TlsEccCurve [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

This Command disables the Elliptic Curve Cryptography (ECC) cipher suites available for
TLS(Transport Layer Security) for a computer.

## EXAMPLES

### Example 1

```powershell
Disable-TlsEccCurve -Name curve25519
```

This will disable the ECC Curve `curve25519`.

## PARAMETERS

### -Name

Specifies the name of the ECC curve to disable.

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
