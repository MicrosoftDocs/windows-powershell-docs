---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.DeviceHealthAttestation.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-DHASActiveSigningCertificate
ms.reviewer:
ms.assetid: 70989F7C-4752-4D12-919D-17588F58DD05
---

# Set-DHASActiveSigningCertificate

## SYNOPSIS
Sets the active signing certificate.

## SYNTAX

```
Set-DHASActiveSigningCertificate [-Thumbprint] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DHASActiveSigningCertificate** cmdlet sets the active signing certificate for the Device Health Attestation service.

You must have administrator rights to run this cmdlet.

## EXAMPLES

### Example 1: Set the active signing certificate
```
PS C:\> Set-DHASActiveSigningCertificate -Thumbprint "0123456789ABCDEF0123456789ABCDEF01234567"
```

This command sets the active signing certificate.

## PARAMETERS

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

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Thumbprint
Specifies the signing certificate thumbprint.
The value must contain only hexadecimal digits (0-9, A-F) and be 40 characters in length.
This value is case-insensitive.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String
The input type is a string for the active signing certificate thumbprint.

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-DHASActiveSigningCertificate](./Get-DHASActiveSigningCertificate.md)

