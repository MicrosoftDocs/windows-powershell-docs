---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.RemoteAttestation.Client.PowerShell.dll-Help.xml
Module Name: HgsClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsclient/get-hgsattestationbaselinepolicy?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HgsAttestationBaselinePolicy
---

# Get-HgsAttestationBaselinePolicy

## SYNOPSIS
Generates an attestation baseline policy.

## SYNTAX

### File (Default)
```
Get-HgsAttestationBaselinePolicy -Path <String> [-Force] [-SkipValidation] [<CommonParameters>]
```

### Console
```
Get-HgsAttestationBaselinePolicy [-Console] [-SkipValidation] [<CommonParameters>]
```

## DESCRIPTION

The `Get-HgsAttestationBaselinePolicy` cmdlet generates an attestation baseline policy. You can use
the policy to configure the attestation service.

This cmdlet gets a byte array that represents the attestation baseline policy from the raw data of
the last full boot from the Trusted Computing Group log of the Trusted Platform Module (TPM).

Be sure to run this cmdlet on a host that is known to have good configuration.

## EXAMPLES

### Example 1: Generate a baseline policy

```powershell
Get-HgsAttestationBaselinePolicy -Path 'C:\Logs\AttestationBaselinePolicy001' -Force
```

This command generates a byte array that represents the baseline policy in the file `C:\Logs\AttestationBaselinePolicy001`.

## PARAMETERS

### -Console

Indicates that this cmdlet operates in console mode.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Console
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Indicates that this cmdlet overwrites an existing file that the **Output** object specifies.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: File
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Specifies a file path.
This cmdlet writes the policy to the file that this parameter specifies.

```yaml
Type: System.String
Parameter Sets: File
Aliases: FilePath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipValidation

Indicates that this cmdlet skips validation.

```yaml
Type: System.Diagnostics.Switch
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Byte[]

## NOTES

## RELATED LINKS
