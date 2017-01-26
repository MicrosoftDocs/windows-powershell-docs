---
author: brianlic-msft
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
title: Remove-HgsAttestationPolicy
ms.assetid: BD9FD7B7-76A6-42E0-8BAD-4A3DA7E4FD94
---

# Remove-HgsAttestationPolicy

## SYNOPSIS
Removes an attestation policy from HGS.

## SYNTAX

```
Remove-HgsAttestationPolicy [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HgsAttestationPolicy** cmdlet removes an attestation policy from Host Guardian Service (HGS).
Specify the policy to remove by name.

## EXAMPLES

### Example 1: Remove a policy
```
PS C:\>Remove-HgsAttestationPolicy -Name "BaselineTpmPolicy16"
```

This command removes the attestation policy named BaselineTpmPolicy16.

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
Specifies the name of the policy that this cmdlet removes.

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

## NOTES

## RELATED LINKS

[Disable-HgsAttestationPolicy](./Disable-HgsAttestationPolicy.md)

[Enable-HgsAttestationPolicy](./Enable-HgsAttestationPolicy.md)

[Get-HgsAttestationPolicy](./Get-HgsAttestationPolicy.md)

