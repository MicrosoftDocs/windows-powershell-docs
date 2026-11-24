---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.RemoteAttestation.Server.PowerShell.dll-Help.xml
Module Name: HgsAttestation
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsattestation/disable-hgsattestationpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-HgsAttestationPolicy
---

# Disable-HgsAttestationPolicy

## SYNOPSIS
Disables an attestation policy in HGS.

## SYNTAX

```
Disable-HgsAttestationPolicy [-Name] <String> [-PolicyVersion <PolicyVersion>] [-Stage] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Disable-HgsAttestationPolicy** cmdlet disables an attestation policy in the Host Guardian Service (HGS).
Specify the policy to disable by name.

## EXAMPLES

### Example 1: Disable a policy
```
PS C:\> Disable-HgsAttestationPolicy -Name "BaselineTpmPolicy16"
```

This command disables the attestation policy named BaselineTpmPolicy16.
After you run this command, any guarded host that requires this policy can no longer obtain new attestation certificates.

## PARAMETERS

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

### -PolicyVersion
Reserved for future use.

```yaml
Type: PolicyVersion
Parameter Sets: (All)
Aliases:
Accepted values: None, PolicyVersion1503, PolicyVersion1704

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stage
Reserved for future use.

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

