---
description: Exports AD FS threat detection module configuration data.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: adfs
ms.date: 10/21/2021
online version: https://docs.microsoft.com/powershell/module/adfs/export-adfsthreatdetectionmoduleconfiguration?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-AdfsThreatDetectionModuleConfiguration
---

# Export-AdfsThreatDetectionModuleConfiguration

## SYNOPSIS
Exports AD FS threat detection module configuration data.

## SYNTAX

```
Export-AdfsThreatDetectionModuleConfiguration -Name <String> -ConfigurationFilePath <String>
 [<CommonParameters>]
```

## DESCRIPTION
The **Export-AdfsThreatDetectionModule** cmdlet exports an AD FS module's configuration data to a
comma separated file.

## EXAMPLES

### Example 1: Export an AD FS threat detection module configuration data.
```powershell
PS> Export-AdfsThreatDetectionModule -Name "IPBlockPlugin" -ConfigurationFilePath "C:\extensions\authconfigdb.csv"
```

Exports AD FS threat detection module `IPBlockPlugin` configuration data comma separated file in the
file path `C:\extensions\authconfigdb.csv`.

## PARAMETERS

### -ConfigurationFilePath
Specifies the fully qualified file path to export the AD FS threat detection module configuration
data.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the friendly name.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
