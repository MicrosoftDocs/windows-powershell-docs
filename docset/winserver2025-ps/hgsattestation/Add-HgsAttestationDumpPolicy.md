---
external help file: Microsoft.Windows.RemoteAttestation.Server.PowerShell.dll-Help.xml
Module Name: HgsAttestation
online version: https://learn.microsoft.com/powershell/module/hgsattestation/add-hgsattestationdumppolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-HgsAttestationDumpPolicy
---

# Add-HgsAttestationDumpPolicy

## SYNOPSIS
Adds an authorized dump encryption key to HGS.

## SYNTAX

### Console (Default)
```
Add-HgsAttestationDumpPolicy [-PublicKeyHash] <String> -Name <String> [-PolicyVersion <PolicyVersion>] [-Stage]
 [-WhatIf] [-Confirm]
```

### File
```
Add-HgsAttestationDumpPolicy [-Path] <String> [-Name <String>] [-PolicyVersion <PolicyVersion>] [-Stage]
 [-WhatIf] [-Confirm]
```

## DESCRIPTION
The **Add-HgsAttestationDumpPolicy** cmdlet authorizes the specified key to be used to encrypt memory dumps on a Hyper-V host.
Only hosts that encrypt dumps using an authorized key and hosts that do not allow any memory dumps will be able to successfully attest.

## EXAMPLES

### Example 1
```
PS C:\> Add-HgsAttestationDumpPolicy -PublicKeyHash 'e91c254ad58860a02c788dfb5c1a65d6a8846ab1dc649631c7db16fef4af2dec' -Name 'Contoso Dump Encryption'
```

Adds the dump encryption key with the specified SHA256 public key hash to HGS.

### Example 2
```
PS C:\> Add-HgsAttestationDumpPolicy -Path 'C:\temp\TpmBaselineWithDumpEncryption.tcglog' -Name 'Contoso Dump Encryption'
```

Adds the dump encryption key to HGS using a TCG log (TPM baseline) obtained after a host was configured to use dump encryption.

## PARAMETERS

### -Name
Friendly name for the dump policy.

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
Specifies the path of a TPM baseline file (TCG log) that contains the public key hash of a dump encryption certificate.
The TPM baseline specified should be obtained after configuring a Hyper-V host to use dump encryption.

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

### -PublicKeyHash
SHA256 hash of the public key of the certificate used for dump encryption.

```yaml
Type: String
Parameter Sets: Console
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.String


## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

