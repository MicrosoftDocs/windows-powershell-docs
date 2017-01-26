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
title: Get-HgsAttestationPolicy
ms.assetid: AE709CBE-1E14-4897-853B-577F84E8B435
---

# Get-HgsAttestationPolicy

## SYNOPSIS
Gets HGS attestation policies.

## SYNTAX

```
Get-HgsAttestationPolicy [-PolicyType <AttestationPolicyType[]>] [[-Name] <String>]
 [-State <AttestationPolicyState>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HgsAttestationPolicy** cmdlet gets Host Guardian Service (HGS) attestation policies.

## EXAMPLES

### Example 1: Get all policies
```
PS C:\>Get-HgsAttestationPolicy
```

This command gets all policies that are currently configured for the Attestation service.

### Example 2: Get a policy by name
```
PS C:\>Get-HgsAttestationPolicy -Name "BaselineTpmPolicy16"
```

This command gets the policy named BaselineTpmPolicy16.

### Example 3: Get policies by type
```
PS C:\>Get-HgsAttestationPolicy -PolicyType Tpm
```

This command gets policies that have the type Tpm.

### Example 4: Get all enabled policies
```
PS C:\>Get-HgsAttestationPolicy -State Enabled
```

This command gets all enabled policies.

## PARAMETERS

### -Name
Specifies the name of the policy that this cmdlet gets.
Use wildcard characters to get more than one policy.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PolicyType
Specifies the type of the policies that this cmdlet gets.

```yaml
Type: AttestationPolicyType[]
Parameter Sets: (All)
Aliases: 
Accepted values: Unknown, SecureBootEnabled, SecureBootSettings, CiPolicy, UefiDebugDisabled, FullBoot, VsmIdkPresent, BitLockerEnabled, IommuEnabled, PagefileEncryptionEnabled, HypervisorEnforcedCiPolicy, NoHibernation, NoDumps, DumpEncryption, DumpEncryptionKey

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State
Specifies the state of the policies that this cmdlet gets.
The acceptable values for this parameter are:

- Enabled 
- Disabled  
- Locked

```yaml
Type: AttestationPolicyState
Parameter Sets: (All)
Aliases: 
Accepted values: Disabled, Enabled, Locked

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String
You can pipe strings to this cmdlet.

## OUTPUTS

### AttestationPolicyInfo
This cmdlet returns attestation policy information.

## NOTES

## RELATED LINKS

[Disable-HgsAttestationPolicy](./Disable-HgsAttestationPolicy.md)

[Enable-HgsAttestationPolicy](./Enable-HgsAttestationPolicy.md)

[Remove-HgsAttestationPolicy](./Remove-HgsAttestationPolicy.md)

