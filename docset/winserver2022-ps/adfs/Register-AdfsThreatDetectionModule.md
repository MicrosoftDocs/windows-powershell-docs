---
description: Registers an AD FS threat detection module.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: adfs
ms.date: 10/01/2021
online version: https://docs.microsoft.com/powershell/module/adfs/register-adfsthreatdetectionmodule?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Register-AdfsThreatDetectionModule
---

# Register-AdfsThreatDetectionModule

## SYNOPSIS
Registers an AD FS threat detection module.

## SYNTAX

```
Register-AdfsThreatDetectionModule [-TypeName] <String> [-Name] <String> [-ConfigurationFilePath <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Register-AdfsThreatDetectionModule** cmdlet registers an AD FS module to read authentication
request headers and implement your own risk assessment logic. The implemented code (plug-in) then
runs in line with AD FS authentication process. AD FS executes the code for each authentication
request and take appropriate action as per the implemented logic.

For more information, see
[Build Plug-ins with AD FS 2019 Risk Assessment Model](/windows-server/identity/ad-fs/development/ad-fs-risk-assessment-model).

## EXAMPLES

### Example 1: Register an AD FS threat detection module
```powershell
PS> Register-AdfsThreatDetectionModule -Name "IPBlockPlugin" -TypeName "ThreatDetectionModule.UserRiskAnalyzer, ThreatDetectionModule, Version=10.0.0.0, Culture=neutral, PublicKeyToken=5ca1ab136ef96b35" -ConfigurationFilePath "C:\extensions\authconfigdb.csv"
```

Registers an AD FS threat detection module `ThreatDetectionModule` and sets the configuration data
file path to a comma separated file named `authconfigdb.csv`.

## PARAMETERS

### -ConfigurationFilePath
Specifies the fully qualified file path of a file that contains the module configuration data.

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

### -Name
Specifies the friendly name.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeName
Specifies the fully qualified type of the AD FS detection module following the pattern
`<class name that implements interface>, <DLL name>, Version=<version number>, Culture=<culture>, PublicKeyToken=<Public key token for the DLL>`

For example, `-TypeName "ThreatDetectionModule.UserRiskAnalyzer, ThreatDetectionModule, Version=10.0.0.0, Culture=neutral, PublicKeyToken=5ca1ab1e6ef96b35"`

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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
