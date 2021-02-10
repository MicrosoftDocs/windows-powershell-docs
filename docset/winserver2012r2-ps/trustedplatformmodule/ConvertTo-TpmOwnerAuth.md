---
external help file: Microsoft.Tpm.Commands.dll-Help.xml
Module Name: TrustedPlatformModule
online version: 
schema: 2.0.0
title: ConvertTo-TpmOwnerAuth
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 1BF5CA4A-9E9B-4C8C-8B7D-ECC6FF0716EF
ms.author: v-kaunu
ms.reviewer: brianlic
---

# ConvertTo-TpmOwnerAuth

## SYNOPSIS
Creates a TPM owner authorization value from a supplied string.

## SYNTAX

```
ConvertTo-TpmOwnerAuth [-PassPhrase] <String> [<CommonParameters>]
```

## DESCRIPTION
The **ConvertTo-TpmOwnerAuth** cmdlet creates a Trusted Platform Module (TPM) owner authorization value based on a pass phrase string.
A computer requires an owner authorization value to manage a TPM.

For more information on TPM, see the Trusted Platform Module Technology Overviewhttp://technet.microsoft.com/en-us/library/jj131725.aspx in the Technet library at http://technet.microsoft.com/en-us/library/jj131725.aspx.

## EXAMPLES

### Example 1: Convert to owner authorization value
```
PS C:\> ConvertTo-TpmOwnerAuth -PassPhrase "Saturn1977&&"
puJvGK4O6Qvl0loP8r1bIxipDVo=
```

This command converts the string Saturn1977&& to an owner authorization value.

## PARAMETERS

### -PassPhrase
Specifies a pass phrase string.
This cmdlet converts the pass phrase to an owner authorization value.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String
A user-supplied pass phrase string.

## OUTPUTS

### String
An owner authorization value.

## NOTES

## RELATED LINKS

[Import-TpmOwnerAuth](./Import-TpmOwnerAuth.md)

[Set-TpmOwnerAuth](./Set-TpmOwnerAuth.md)

