---
external help file: Microsoft.Windows.RemoteAttestation.Server.PowerShell.dll-Help.xml
Module Name: HgsAttestation
online version: https://learn.microsoft.com/powershell/module/hgsattestation/add-hgsattestationcipolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-HgsAttestationCIPolicy
---

# Add-HgsAttestationCIPolicy

## SYNOPSIS
Authorizes a trusted code integrity policy to be used by hosts attesting against HGS.

## SYNTAX

### Console
```
Add-HgsAttestationCIPolicy [-InputObject] <Byte[]> -Name <String> [-PolicyVersion <PolicyVersion>] [-Stage]
 [-WhatIf] [-Confirm]
```

### File
```
Add-HgsAttestationCIPolicy [-Path] <String> [-Name <String>] [-PolicyVersion <PolicyVersion>] [-Stage]
 [-WhatIf] [-Confirm]
```

## DESCRIPTION
The **Add-HgsAttestationCIPolicy** cmdlet adds an attestation policy based on a trusted code integrity policy to HGS.
When HGS is configured to use TPM attestation, hosts will need to use one of the code integrity policies registered with HGS to successfully pass attestation.
Use the **New-CIPolicy** and **ConvertFrom-CIPolicy** cmdlets to create a binary code integrity policy that can be passed to this cmdlet.

HGS will not know which software is allowed or disallowed by your policy, nor will it know which policy rules (e.g. enforced CI, reboot actions) are configured in the policy.
You should choose a descriptive name for your policy to ensure you know what your policy covers for future reference when reviewing authorized policies.

## EXAMPLES

### Example 1
```
PS C:\> Add-HgsAttestationCIPolicy -Path C:\temp\WS2016-Enforced.p7b -Name "Windows Server 2016 Enforced CI Policy"
```

Adds the binary code integrity policy file to HGS and names the policy "Windows Server 2016 Enforced CI Policy"

## PARAMETERS

### -InputObject
Byte array containing the contents of a binary code integrity policy file.

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
Friendly name for the code integrity policy.

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
Specifies the path of a file that contains the code integrity policy, in binary form.
The file typically has a .p7b or .bin extension.

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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Byte[], System.String
This cmdlet accepts a code integrity policy as a **Byte** array or filename.

## OUTPUTS

### AttestationPolicyInfo
This cmdlet returns attestation policy information.

## NOTES

## RELATED LINKS

