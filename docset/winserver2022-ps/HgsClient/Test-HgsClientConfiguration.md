---
external help file: HgsClient-help.xml
Module Name: HgsClient
online version: https://learn.microsoft.com/powershell/module/hgsclient/test-hgsclientconfiguration?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-HgsClientConfiguration
---

# Test-HgsClientConfiguration

## SYNOPSIS
Forces the HGS client to attest against the configured attestation servers.

## SYNTAX

### Primary
```
Test-HgsClientConfiguration [-UsePrimary]
```

### Fallback
```
Test-HgsClientConfiguration [-UseFallback]
```

## DESCRIPTION
The **Test-HgsClientConfiguration** cmdlet forces the HGS client to attest against an HGS server and report back on the attestation attempt.
Any cached attestation health certificates from recent attestation attempts will be ignored.

## EXAMPLES

### Example 1
```
PS C:\> Test-HgsClientConfiguration
```

Performs an attestation attempt using the primary HGS server.
If the primary HGS server cannot be reached and fallback URLs are configured, the fallback HGS server will be used.

### Example 2
```
PS C:\> Test-HgsClientConfiguration -UsePrimary
```

Performs an attestation attempt using the primary HGS server.
If the primary HGS server cannot be reached, the cmdlet will fail.

### Example 3
```
PS C:\> Test-HgsClientConfiguration -UseFallback
```

Performs an attestation attempt using the fallback HGS server.

## PARAMETERS

### -UseFallback
Specifies that the HGS client should only attest against the fallback attestation server.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Fallback
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UsePrimary
Specifies that the HGS client should only attest against the primary attestation server.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Primary
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None


## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance
An object containing the attestation server URL used and the results of the attestation attempt.

## NOTES

## RELATED LINKS

