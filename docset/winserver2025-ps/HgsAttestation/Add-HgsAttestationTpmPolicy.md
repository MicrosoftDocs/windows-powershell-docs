---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.RemoteAttestation.Server.PowerShell.dll-Help.xml
Module Name: HgsAttestation
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsattestation/add-hgsattestationtpmpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-HgsAttestationTpmPolicy
---

# Add-HgsAttestationTpmPolicy

## SYNOPSIS
Adds an attestation policy based on TPM 2.0 hardware to HGS.

## SYNTAX

### Console
```
Add-HgsAttestationTpmPolicy [-InputObject] <Byte[]> -Name <String> [-PolicyVersion <PolicyVersion>] [-Stage]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### File
```
Add-HgsAttestationTpmPolicy [-Path] <String> [-Name <String>] [-PolicyVersion <PolicyVersion>] [-Stage]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-HgsAttestationTpmPolicy** cmdlet adds an attestation policy based on trusted platform module (TPM) 2.0 hardware to the Host Guardian Service (HGS).
Specify a log, in Trusted Computing Group (TCG) format, that you obtain by using the **Get-HgsAttestationBaselinePolicy** cmdlet.

## EXAMPLES

### Example 1: Add a policy
```
PS C:\> Add-HgsAttestationTpmPolicy -Name "BaselineTpmPolicy17" -Path "C:\Hgs\BaselineTcgLog"
```

This command adds a policy named BaselineTpmPolicy17 to the Attestation service.
The Path parameter specifies the TCG log that you create by using **Get-HgsAttestationBaselinePolicy** cmdlet.

## PARAMETERS

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

### Byte[], String
This cmdlet accepts a TCG log as a **Byte** array or a file name.

## OUTPUTS

### AttestationPolicyInfo
This cmdlet returns attestation policy information.

## NOTES

## RELATED LINKS

