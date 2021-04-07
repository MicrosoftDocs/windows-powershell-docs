---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.WindowsAuthenticationProtocols.Commands.dll-Help.xml
manager: jasgro
Module Name: TLS
ms.author: v-kaunu
ms.date: 05/09/2017
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/tls/disable-tlsecccurve?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-TlsEccCurve
---

# Disable-TlsEccCurve

## SYNOPSIS
Disables the Elliptic Curve Cryptography (ECC) cipher suites available for TLS(Transport Layer Security) for a computer.

## SYNTAX

```
Disable-TlsEccCurve [-Name] <String> [-WhatIf] [-Confirm]
```

## DESCRIPTION
This Command disables the Elliptic Curve Cryptography (ECC) cipher suites available for TLS(Transport Layer Security) for a computer.

## EXAMPLES

### Example 1
```
PS C:\> Disable-TlsEccCurve -Name curve25519
```

This will disable the ECC Curve "curve25519".

## PARAMETERS

### -Name
Specifies the name of the ECC curve to disable.

```yaml
Type: String
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
Type: SwitchParameter
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### System.String


## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

