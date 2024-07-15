---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: HgsClient-help.xml
Module Name: HgsClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsclient/set-hgsclientconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-HgsClientConfiguration
---

# Set-HgsClientConfiguration

## SYNOPSIS
Modifies the configuration of a Host Guardian Service client.

## SYNTAX

### ChangeToLocalMode
```
Set-HgsClientConfiguration [-EnableLocalMode] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FullSecureHostingServiceMode
```
Set-HgsClientConfiguration -KeyProtectionServerUrl <String> -AttestationServerUrl <String>
 -FallbackKeyProtectionServerUrl <String> -FallbackAttestationServerUrl <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SecureHostingServiceMode
```
Set-HgsClientConfiguration -KeyProtectionServerUrl <String> -AttestationServerUrl <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-HgsClientConfiguration** cmdlet modifies the configuration of a Host Guardian Service client.
You can configure the client in either local mode or Host Guardian Service mode.
In local mode, there is no attestation and the client keeps key material.

## EXAMPLES

### Example 1: Set an attestation and key protection servers
```
PS C:\> Set-HgsClientConfiguration -AttestationServerUrl "https://DemoHgs.Contoso.com/Attestation" -KeyProtectionServerUrl "https://DemoHgs.Contoso.com/KeyProtection"
```

This command configures the URLs used by the attestation client and the key protection client.
Use this command to configure the local host to run in Host Guardian Service mode.

### Example 2: Change the mode to Local
```
PS C:\> Set-HgsClientConfiguration -EnableLocalMode
```

This command changes the Host Guardian Service client from Host Guardian Service mode to Local mode.
This command resets the attestation server URL and the key protection server URL.

## PARAMETERS

### -AttestationServerUrl
Specifies the URL of an attestation server.
A Host Guardian Service client in Secure Hosting Service mode uses the server that this parameter specifies.

```yaml
Type: String
Parameter Sets: FullSecureHostingServiceMode, SecureHostingServiceMode
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLocalMode
Indicates that this cmdlet changes the mode of client from Host Guardian Service to Local mode.
A change in mode to Local resets the attestation server and key protection server URLs.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ChangeToLocalMode
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FallbackAttestationServerUrl
Specifies the URL of an attestation server to use if the primary attestation server cannot be reached.

```yaml
Type: String
Parameter Sets: FullSecureHostingServiceMode
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FallbackKeyProtectionServerUrl
Specifies the URL of a key protection server to use if the primary attestation server cannot be reached.

```yaml
Type: String
Parameter Sets: FullSecureHostingServiceMode
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyProtectionServerUrl
Specifies the URL of a key protection server.
A Host Guardian Service client in Secure Hosting Service mode uses the server that this parameter specifies.

```yaml
Type: String
Parameter Sets: FullSecureHostingServiceMode, SecureHostingServiceMode
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
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
Type: System.Management.Automation.SwitchParameter
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

### CimInstance#MSFT_HgsClientConfiguration
An HGS client configuration object containing information about the operating mode, configured URLs, and result of the most recent attestation attempt, if applicable.

## NOTES

## RELATED LINKS

[Get-HgsClientConfiguration](./Get-HgsClientConfiguration.md)

