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
title: Disable-HgsAttestationPolicy
ms.assetid: 066AFCBB-0066-4E5C-9269-D708A3C496DE
---

# Disable-HgsAttestationPolicy

## SYNOPSIS
Disables an attestation policy in HGS.

## SYNTAX

```
Disable-HgsAttestationPolicy [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-HgsAttestationPolicy** cmdlet disables an attestation policy in the Host Guardian Service (HGS).
Specify the policy to disable by name.

## EXAMPLES

### Example 1: Disable a policy
```
PS C:\>Disable-HgsAttestationPolicy -Name "BaselineTpmPolicy16"
```

This command disables the attestation policy named BaselineTpmPolicy16.
After you run this command, any guarded host that requires this policy can no longer obtain new attestation certificates.

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
Specifies the name of the policy that this cmdlet disables.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### AttestationPolicyInfo
This cmdlet returns an **AttestationPolicyInfo** object.

## NOTES

## RELATED LINKS

[Enable-HgsAttestationPolicy](./Enable-HgsAttestationPolicy.md)

[Get-HgsAttestationPolicy](./Get-HgsAttestationPolicy.md)

[Remove-HgsAttestationPolicy](./Remove-HgsAttestationPolicy.md)

