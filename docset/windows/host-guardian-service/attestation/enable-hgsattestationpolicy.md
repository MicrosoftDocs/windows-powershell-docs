---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: brianlic
author: brianlic-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.RemoteAttestation.Server.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Enable-HgsAttestationPolicy
ms.assetid: 603AAC8C-B18E-47AB-BF1A-EDFDD1F7ACAC
---

# Enable-HgsAttestationPolicy

## SYNOPSIS
Enables an attestation policy in HGS.

## SYNTAX

```
Enable-HgsAttestationPolicy [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-HgsAttestationPolicy** cmdlet enables an attestation policy in the Host Guardian Service (HGS).
Specify the policy to enable by name.

## EXAMPLES

### Example 1: Enable a policy
```
PS C:\> Enable-HgsAttestationPolicy -Name "BaselineTpmPolicy16"
```

This command enables the attestation policy named BaselineTpmPolicy16.
This policy was disabled.
After you run this command, any guarded host that matches this policy can obtain new attestation certificates.

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

### -Name
Specifies the name of the policy that this cmdlet enables.

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

## OUTPUTS

### AttestationPolicyInfo
This cmdlet returns an **AttestationPolicyInfo** object.

## NOTES

## RELATED LINKS

[Disable-HgsAttestationPolicy](./Disable-HgsAttestationPolicy.md)

[Get-HgsAttestationPolicy](./Get-HgsAttestationPolicy.md)

[Remove-HgsAttestationPolicy](./Remove-HgsAttestationPolicy.md)

