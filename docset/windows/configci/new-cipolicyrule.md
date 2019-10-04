---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ConfigCI.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: New-CIPolicyRule
ms.reviewer:
ms.assetid: C85AE8E8-F3B3-445B-AC5A-7E095685B488
---

# New-CIPolicyRule

## SYNOPSIS
Generates Code Integrity policy rules for drivers.

## SYNTAX

### DriverFileList
```
New-CIPolicyRule [-DriverFiles <DriverFile[]>] -Level <RuleLevel> [-Fallback <RuleLevel[]>] [-Deny]
 [-ScriptFileNames] [<CommonParameters>]
```

### DriverFilePath
```
New-CIPolicyRule -DriverFilePath <String> -Level <RuleLevel> [-Fallback <RuleLevel[]>] [-Deny]
 [-ScriptFileNames] [<CommonParameters>]
```

## DESCRIPTION
The **New-CIPolicyRule** cmdlet generates Code Integrity policy rules for drivers.
Specify a rule level and an array of **DriverFile** objects or the path of a driver.

## EXAMPLES

### Example 1: Create policy rules for drivers
```
PS C:\> $DriverFiles = Get-SystemDriver -ScanPath '.\temp\' -UserPEs -OmitPaths '.\temp\ConfigCITestBinaries' -NoScript
PS C:\> New-CIPolicyRule -Level FileName -DriverFiles $DriverFiles
Scan completed successfully


Name           : \\?\E:\cmdlets\temp\Microsoft.ConfigCI.Commands.dll FileRule
Id             : ID_ALLOW_A_1
TypeId         : Allow
Root           : 
FileVersionRef : 
Wellknown      : False
Ekus           : 
Exceptions     : 
FileAttributes : 
FileException  : False
UserMode       : False

Name           : \\?\E:\cmdlets\temp\Microsoft.ConfigCI.Commands.Tests.dll FileRule
Id             : ID_ALLOW_A_3
TypeId         : Allow
Root           : 
FileVersionRef : 
Wellknown      : False
Ekus           : 
Exceptions     : 
FileAttributes : 
FileException  : False
UserMode       : False

Name           : \\?\E:\cmdlets\temp\Microsoft.PackageInspector.Tests.dll FileRule
Id             : ID_ALLOW_A_5
TypeId         : Allow
Root           : 
FileVersionRef : 
Wellknown      : False
Ekus           : 
Exceptions     : 
FileAttributes : 
FileException  : False
UserMode       : False
```

The first command gets drivers by using the **Get-SystemDriver** cmdlet, and then stores them in the $DriverFiles variable.

The second command creates policy rules at the file name level for the drivers in $DriverList.
For this example, we present only the first few rules.

### Example 2: Create policy rules for drivers and include a fallback value
```
PS C:\> New-CIPolicyRule -Level Publisher -Fallback Hash -DriverFiles $DriverFiles
"Scan completed successfully"


Name           : \\?\E:\cmdlets\temp\Microsoft.ConfigCI.Commands.dll Hash Sha1
Id             : ID_ALLOW_A_F
TypeId         : Allow
Root           : 
FileVersionRef : 
Wellknown      : False
Ekus           : 
Exceptions     : 
FileAttributes : 
FileException  : False
UserMode       : False

Name           : \\?\E:\cmdlets\temp\Microsoft.ConfigCI.Commands.dll Hash Sha256
Id             : ID_ALLOW_A_10
TypeId         : Allow
Root           : 
FileVersionRef : 
Wellknown      : False
Ekus           : 
Exceptions     : 
FileAttributes : 
FileException  : False
UserMode       : False

Name           : \\?\E:\cmdlets\temp\Microsoft.ConfigCI.Commands.dll Hash Page Sha1
Id             : ID_ALLOW_A_11
TypeId         : Allow
Root           : 
FileVersionRef : 
Wellknown      : False
Ekus           : 
Exceptions     : 
FileAttributes : 
FileException  : False
UserMode       : False
```

This command generates rule at the Publisher level for the same drivers from the previous example.
For files that are unsigned, the cmdlet creates Hash rules, as a fallback.
For this example, we present only the first few rules.

### Example 3: Specify a policy rule for a kernel component
```
PS C:\> New-CIPolicyRule -DriverFilePath '.\temp\ConfigCITestBinaries\ci.dll' -Level Publisher
Scan completed successfully


Name           : MSIT Test CodeSign CA 3
Id             : ID_SIGNER_S_B
TypeId         : Allow
Root           : FA6B9A2230CE08BCA81D096B28CF495672401D3A43A0D285CF352464A6C9C7FD
FileVersionRef : 
Wellknown      : False
Ekus           : 
Exceptions     : 
FileAttributes : 
FileException  : False
UserMode       : False

Name           : MSIT Test CodeSign CA 3
Id             : ID_SIGNER_S_C
TypeId         : Allow
Root           : FA6B9A2230CE08BCA81D096B28CF495672401D3A43A0D285CF352464A6C9C7FD
FileVersionRef : 
Wellknown      : False
Ekus           : 
Exceptions     : 
FileAttributes : 
FileException  : False
UserMode       : True
```

This command generates a publisher rule for the specific file named ci.dll.
The file ci.dll is a kernel component.
Therefore, the cmdlet generates both a kernel rule and a user mode rule.

## PARAMETERS

### -Deny
Indicates that this cmdlet creates deny rules instead of the default allow rules.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: d

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DriverFilePath
Specifies the path of a driver on which this cmdlet bases a rule.

```yaml
Type: String
Parameter Sets: DriverFilePath
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DriverFiles
Specifies an array of **DriverFile** objects on which this cmdlet bases rules.
To obtain a driver file, use the **Get-SystemDriver** cmdlet.

```yaml
Type: DriverFile[]
Parameter Sets: DriverFileList
Aliases: df

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Fallback
Specifies an array of levels of detail for generated rules.
If this cmdlet cannot generate a rule at the specified level, this cmdlet attempts to generate it at a fallback level.
The acceptable values for this parameter are the same as for the **Level** parameter.
If you specify multiple fallback levels, this cmdlet tries them in order.

```yaml
Type: RuleLevel[]
Parameter Sets: (All)
Aliases: 
Accepted values: None, Hash, FileName, FilePath, SignedVersion, PFN, Publisher, FilePublisher, LeafCertificate, PcaCertificate, RootCertificate, WHQL, WHQLPublisher, WHQLFilePublisher

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Level
Specifies the primary level of detail for generated rules. Refer to [WDAC File Rule Levels](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/select-types-of-rules-to-create#windows-defender-application-control-file-rule-levels) for acceptable parameter values and descriptions.

```yaml
Type: RuleLevel
Parameter Sets: (All)
Aliases: l
Accepted values: None, Hash, FileName, FilePath, SignedVersion, PFN, Publisher, FilePublisher, LeafCertificate, PcaCertificate, RootCertificate, WHQL, WHQLPublisher, WHQLFilePublisher

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptFileNames


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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Rule
This cmdlet returns the rules that it creates.

## NOTES

## RELATED LINKS

[Get-SystemDriver](./Get-SystemDriver.md)

