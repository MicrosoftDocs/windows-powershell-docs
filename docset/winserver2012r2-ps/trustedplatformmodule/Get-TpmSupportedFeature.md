---
external help file: Microsoft.Tpm.Commands.dll-Help.xml
Module Name: TrustedPlatformModule
online version: 
schema: 2.0.0
title: Get-TpmSupportedFeature
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 6D522831-D48C-48C5-A2A3-AA7E7C2F0693
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-TpmSupportedFeature

## SYNOPSIS
Verifies whether a TPM supports specified features.

## SYNTAX

```
Get-TpmSupportedFeature [[-FeatureList] <StringCollection>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-TpmSupportedFeature** cmdlet verifies whether a Trusted Platform Module (TPM) supports specified TPM features.
Not all TPMs support all features.

## EXAMPLES

### Example 1: Verify support for key attestation
```
PS C:\> Get-TpmSupportedFeature -FeatureList "Key Attestation"
key attestation
```

This command verifies whether TPM supports the key attestation feature.
The cmdlet displays the string, key attestation, so TPM supports that feature.

## PARAMETERS

### -FeatureList
Specifies feature names as a string collection.
The cmdlet verifies the features that you specify.
If you specify an empty collection, $Null, or do not include this parameter, the cmdlet verifies all features.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### StringCollection
This cmdlet accepts a collection of features to verify.

## OUTPUTS

### StringCollection
This cmdlet generates a **StringCollection** object that contains features that the TPM of the computer supports.

## NOTES

## RELATED LINKS

