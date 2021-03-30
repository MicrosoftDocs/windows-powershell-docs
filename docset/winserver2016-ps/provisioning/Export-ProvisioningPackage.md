---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: provcmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.author: v-kaunu
ms.date: 05/09/2017
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Export-ProvisioningPackage
ms.reviewer:
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

## EXAMPLES

### Example 1
```
PS C:\> Export-ProvisioningPackage -PackageId {e2ea11f5-d8b0-4db9-bf96-8c909dc2fed5} -OutputFolder D:\Package
```

This example extracts the content of a Package specifying it's PackageId to the specified folder.

## PARAMETERS

### -AllowClobber
{{Fill AllowClobber Description}}

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
Only exports the Windows provisioning answer file

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
{{Fill ConnectedDevice Description}}

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
Specifies a path to store logs files resulting from the export operation

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
Specifies the path to the output directory

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
Id of the Package to be extracted

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
Path to the package to be extracted

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
{{Fill RuntimeMetadata Description}}

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
{{Fill WprpFile Description}}

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

