---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.KpsServer.Administration.dll-Help.xml
Module Name: HgsKeyProtection
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgskeyprotection/import-hgskeyprotectionstate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-HgsKeyProtectionState
---

# Import-HgsKeyProtectionState

## SYNOPSIS
Imports previously exported Key Protection Service configuration and certificates.

## SYNTAX

### File
```
Import-HgsKeyProtectionState -Password <SecureString> [-Force] [-IgnoreImportFailures] [[-Path] <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### XML
```
Import-HgsKeyProtectionState -Password <SecureString> [-Force] [-IgnoreImportFailures] [[-Xml] <XmlDocument>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Import-HgsKeyProtectionState** cmdlet imports previously exported configuration of Key Protection Service from a file referenced by the path parameter.
If the path parameter is not provided, the configuration state can be passed in as an XmlDocument to the *Xml* parameter.
If the configuration contains certificates that were added to the service with pfx (containing private key), then the cmdlet also imports those certificates.
If the configuration contains certificates that were previously added to Key Protection Certificate as pfx, then the password supplied must match the password that was provided at the time of exporting the configuration.

## EXAMPLES

### Example 1: Import Key Protection Service state from a file
```
PS C:\> Import-HgsKeyProtectionState -Path "C:\example\kps.config" -Password $Password
```

This command imports configuration state to a Key Protection Service from the file referenced by the path parameter.
If the file contains private keys for certificates, then the password must be supplied by a secure string referenced by the $Password variable.

### Example 2: Import Key Protection Service state from an XML document
```
PS C:\> Import-HgsKeyProtectionState -Xml $XmlDoc -Password $Password
```

This command imports configuration state to a Key Protection Service from an XML document referenced by the XML parameter.
If the file contains private keys for certificates, then the password must be supplied by a secure string referenced by the $Password variable.

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

### -IgnoreImportFailures
Indicates that this cmdlet ignores import failures.

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
```yaml
Type: String
Parameter Sets: File
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Xml
```yaml
Type: XmlDocument
Parameter Sets: XML
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Export-HgsKeyProtectionState](./Export-HgsKeyProtectionState.md)

