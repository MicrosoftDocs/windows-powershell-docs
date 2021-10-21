---
description: Imports AD FS threat detection module configuration data.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: adfs
ms.date: 10/21/2021
online version: https://docs.microsoft.com/powershell/module/adfs/import-adfsthreatdetectionmoduleconfiguration?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-AdfsThreatDetectionModuleConfiguration
---

# Import-AdfsThreatDetectionModuleConfiguration

## SYNOPSIS
Imports AD FS threat detection module configuration data.

## SYNTAX

```
Import-AdfsThreatDetectionModuleConfiguration -Name <String> -ConfigurationFilePath <String>
 [<CommonParameters>]
```

## DESCRIPTION
The **Import-AdfsThreatDetectionModule** cmdlet imports an AD FS module's configuration data from a
comma separated file.

## EXAMPLES

### Example 1: Import an AD FS threat detection module's configuration data.
```powershell
PS> Import-AdfsThreatDetectionModule -Name "IPBlockPlugin" -ConfigurationFilePath "C:\extensions\authconfigdb.csv"
```

Imports configuration data from a comma separated file located at the file path
`C:\extensions\authconfigdb.csv` into an AD FS threat detection module named `IPBlockPlugin`.

## PARAMETERS

### -ConfigurationFilePath
Specifies the fully qualified file path of a configuration data file to import into the AD FS threat
detection module.

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
