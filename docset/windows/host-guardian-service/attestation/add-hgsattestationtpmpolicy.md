---
author: brianlic
description: 
external help file: Microsoft.Windows.RemoteAttestation.Server.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Add-HgsAttestationTpmPolicy
ms.assetid: 92CD89D0-95EA-49B5-8B2E-C2286E087A76
---

# Add-HgsAttestationTpmPolicy

## SYNOPSIS
Adds an attestation policy based on TPM 2.0 hardware to HGS.

## SYNTAX

### Console
```
Add-HgsAttestationTpmPolicy [-InputObject] <Byte[]> -Name <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### File
```
Add-HgsAttestationTpmPolicy [-Path] <String> [-Name <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-HgsAttestationTpmPolicy** cmdlet adds an attestation policy based on trusted platform module (TPM) 2.0 hardware to the Host Guardian Service (HGS).
Specify a log, in Trusted Computing Group (TCG) format, that you obtain by using the Get-HgsAttestationBaselinePolicy cmdlet.

## EXAMPLES

### Example 1: Add a policy
```
PS C:\>Add-HgsAttestationTpmPolicy -Name "BaselineTpmPolicy17" -Path "C:\Hgs\BaselineTcgLog"
```

This command adds a policy named BaselineTpmPolicy17 to the Attestation service.
The Path parameter specifies the TCG log that you create by using **Get-HgsAttestationBaselinePolicy** cmdlet.

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

### -InputObject
Specifies a TCG log, in binary form, on which this cmdlet bases a policy.

```yaml
Type: Byte[]
Parameter Sets: Console
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the policy that this cmdlet adds.

```yaml
Type: String
Parameter Sets: Console
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: File
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path of a file that contains a TCG log, in binary form.

```yaml
Type: String
Parameter Sets: File
Aliases: FilePath, PSPath

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Byte[], String
This cmdlet accepts a TCG log as a **Byte** array or a file name.

## OUTPUTS

### AttestationPolicyInfo
This cmdlet returns attestation policy information.

## NOTES

## RELATED LINKS

[Add-HgsAttestationCIPolicy](./Add-HgsAttestationCIPolicy.md)

