---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: provcmdlets.dll-Help.xml
Module Name: Provisioning
ms.date: 05/09/2017
online version: https://learn.microsoft.com/powershell/module/provisioning/export-provisioningpackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-ProvisioningPackage
---

# Export-ProvisioningPackage

## SYNOPSIS
Extract the contents of a provisioning package.

## SYNTAX

### Id
```
Export-ProvisioningPackage -PackageId <String> [-OutputFolder] <String> [-AllowClobber] [-AnswerFileOnly]
 [-LogsDirectoryPath <String>] [-WprpFile <String>] [-ConnectedDevice]
```

### Path
```
Export-ProvisioningPackage [-PackagePath] <String> [-OutputFolder] <String> [-AllowClobber] [-AnswerFileOnly]
 [-LogsDirectoryPath <String>] [-WprpFile <String>] [-ConnectedDevice]
```

### Metadata
```
Export-ProvisioningPackage [-RuntimeMetadata] <RuntimeProvPackageMetadata> [-OutputFolder] <String>
 [-AllowClobber] [-AnswerFileOnly] [-LogsDirectoryPath <String>] [-WprpFile <String>] [-ConnectedDevice]
```

## DESCRIPTION
Extract the contents of a provisioning package to the specified folder.

The **Export-ProvisioningPackage** cmdlet is supported on Windows 11 client operating system only.

## EXAMPLES

### Example 1
```
PS C:\> Export-ProvisioningPackage -PackageId {e2ea11f5-d8b0-4db9-bf96-8c909dc2fed5} -OutputFolder D:\Package
```

This example extracts the content of a Package specifying it's PackageId to the specified folder.

## PARAMETERS

### -AllowClobber
Indicates that the cmdlet exports contents even if there's an existing instance.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: Force, Overwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AnswerFileOnly
Indicates that the cmdlet only exports the Windows provisioning answer file.

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

### -ConnectedDevice
Indicates that the provisioning package uses a connected device.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: Device

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogsDirectoryPath
Specifies a path to store logs files resulting from the export operation.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Logs

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputFolder
Specifies the path to the output directory.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Out

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageId
Specifies the ID of the Package to be extracted.

```yaml
Type: String
Parameter Sets: Id
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackagePath
Specifies the path to the package to be extracted.

```yaml
Type: String
Parameter Sets: Path
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RuntimeMetadata
Specifies a runtime provisioning package metadata object.

```yaml
Type: RuntimeProvPackageMetadata
Parameter Sets: Metadata
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WprpFile
Specifies the name of a WPR profile file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Wprp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Windows.Provisioning.ProvCommon.RuntimeProvPackageMetadata


## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

