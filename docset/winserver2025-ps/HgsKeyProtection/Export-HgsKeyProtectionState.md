---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.KpsServer.Administration.dll-Help.xml
Module Name: HgsKeyProtection
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgskeyprotection/export-hgskeyprotectionstate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-HgsKeyProtectionState
---

# Export-HgsKeyProtectionState

## SYNOPSIS
Exports Key Protection Service configuration and certificates.

## SYNTAX

```
Export-HgsKeyProtectionState [-Path <String>] -Password <SecureString> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Export-HgsKeyProtectionState** cmdlet exports configuration of Key Protection Service to a file referenced by the path parameter.
If the path parameter is not provided, the cmdlet outputs the configuration state as XML.
If the configuration contains certificates that were added to the service with pfx (containing private key), then the exported configuration also contains those private keys.
The password parameter is used to protect the private keys that are part of the configuration.
If the configuration contains certificates with private keys in Hardware Security Module (HSM), then the configuration only contains the public certificate.

## EXAMPLES

### Example 1: Export Key Protection Service state to a file
```
PS C:\> Export-HgsKeyProtectionState -Path "C:\example\kps.config" -Password $Password
```

This command exports configuration state of Key Protection Service.
All certificates that were added as a pfx are included in the output which is written to the file referenced by the path parameter.
The private keys are protected with the password specified in the $Password secure string.

### Example 2: Export Key Protection Service state to Xml
```
PS C:\> Export-HgsKeyProtectionState  -Password $Password
```

This command exports configuration state of Key Protection Service as output that can be stored in a variable.
All certificates that were added as a pfx are included in the output.
The private keys are protected with the password specified in the $Password secure string.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

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

### -Password
Specifies the password which protects private keys contained within the exported configuration.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path of the file to which the configuration state is written.

```yaml
Type: String
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

### None
You cannot pipe input to this cmdlet.

## OUTPUTS

### None
This cmdlet outputs XmlDocument that contains Key Protection Service state if Path parameter is not specified.

## NOTES

## RELATED LINKS

[Import-HgsKeyProtectionState](./Import-HgsKeyProtectionState.md)

