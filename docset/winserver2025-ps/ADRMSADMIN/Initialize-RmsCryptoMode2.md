---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
Module Name: ADRMSADMIN
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adrmsadmin/initialize-rmscryptomode2?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Initialize-RmsCryptoMode2
---

# Initialize-RmsCryptoMode2

## SYNOPSIS
Prepares an AD RMS server for transitioning to Cryptographic Mode 2.

## SYNTAX

```
Initialize-RmsCryptoMode2 -FilePath <String[]> [-CspName <String>] [-Regenerate] [-Force] [-Path] <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Initialize-RmsCryptoMode2** cmdlet prepares an Active Directory Rights Management Services (AD RMS) server for transitioning to Cryptographic Mode 2.

Cryptographic Mode 2 is an updated and enhanced AD RMS cryptographic implementation.
It supports 2048-bit RSA encryption and 256-bit length keys using the SHA-2 hashing algorithm (SHA-2/SHA-256) standards.

While this cmdlet is useful for performing the initial steps required in transitioning an AD RMS deployment to Cryptographic Mode 2, additional tasks are required.
First, all client computers in the AD RMS cluster environment must be patched to support this updated and enhanced mode.
Depending on your deployment configuration, you may need to update some or all servers.
When all computers are updated, as the final transition task to Cryptographic Mode 2, you can run the **Update-ADRMS** cmdlet with the *UpdateCryptographicModeOnly* parameter specified to effectively switch the cluster to using mode 2 instead of mode 1.

## EXAMPLES

### Example 1: Export the SLC
```
PS C:\> Initialize-RmsCryptoMode2 -Path "." -FilePath "c:\test.tud"
```

This command exports the server licensor certificate (SLC) for the current AD RMS server to the trusted user domain c:\test.tud for a server that uses centrally managed keys.

### Example 2: Force regeneration of cryptographic mode 2 keys
```
PS C:\> Initialize-RmsCryptoMode2 -Path "." -FilePath "c:\test2.tud" -Regenerate

Initialize cryptographic mode 2

This will regenerate the cryptographic mode 2 key pair.  Are you sure you want to continue?

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

This command forces regeneration of the cryptographic mode 2 keys.

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

### -CspName
Specifies the name of the cryptographic service provider (CSP) to use for generating the mode 2 TUD when this cmdlet is executed.
This CSP must be of the type PROV_RSA_AES to support mode 2 operation (in contrast to mode 1 keys which use the CSP type PROV_RSA_FULL).

The *CspName* parameter is for CSP-based installs only.
If a CSP name is specified for a server with a centrally managed key, an error is returned if this parameter is included in the command.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -FilePath
Specifies the name and location for the file generated when this cmdlet is executed.
This file contains the mode 2 SLC (server licensor certificate) which is exported as part of transitioning a trusted user domain (TUD) to mode operation.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Force
Forces the cmdlet to save (overwrite) an existing file if one is found to exist under the name and location specified as part of the *FilePath* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Path
This parameter is for CSP-based installs only.
If a CSP name is specified for a server with a centrally managed key, an error is returned if this parameter is included in the command.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Regenerate
Forces the AD RMS server to generate a new key even if the cmdlet has previously run.
This overwrites any previously generated key.
Because you can run this cmdlet multiple times, if this parameter is omitted, the same key is exported each subsequent time the cmdlet is run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### string[], string, bool, SwitchParameter

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Using Windows PowerShell with AD RMS](https://go.microsoft.com/fwlink/?LinkId=136806)

