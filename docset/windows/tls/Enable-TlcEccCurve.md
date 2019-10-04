---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.WindowsAuthenticationProtocols.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.author: v-anbarr
ms.date: 2017-05-09
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Enable-TlcEccCurve
ms.reviewer:
---

# Enable-TlsEccCurve

## SYNOPSIS
Enables Elliptic Curve Cryptography (ECC) cipher suites available for TLS.

## SYNTAX

```
Enable-TlsEccCurve [[-Position] <UInt32>] [-Name] <String> [-WhatIf] [-Confirm]
```

## DESCRIPTION
Enables Elliptic Curve Cryptography (ECC) cipher suites available for TLS for a computer.

## EXAMPLES

### Example 1
```
PS C:\> Enable-TlsEccCurve "NistP384" -Position 0
```

This command enables Elliptic Curve Cryptography cipher suite named "NistP384"  at position 0, which is the highest priority.

## PARAMETERS

### -Name
Specifies the name of the ECC cipher suite to enable.

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

### -Position
Specifies the position at which to insert the cipher suite in the ordered list of ECC cipher suites. The cmdlet inserts the cipher suite at the position that this parameter specifies, ahead of any existing cipher suites.

Specify a value of 0 or CRYPT_PRIORITY_TOP to insert the function at the top of the list. Specify a value of 4294967295 or 0xFFFFFFFF or CRYPT_PRIORITY_BOTTOM to insert the function at the end of the list.

```yaml
Type: UInt32
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

