---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: provcmdlets.dll-Help.xml
manager: jasgro
Module Name: Provisioning
ms.author: v-kaunu
ms.date: 05/09/2017
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/provisioning/uninstall-provisioningpackage?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-ProvisioningPackage
---

# Uninstall-ProvisioningPackage

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### Id
```
Uninstall-ProvisioningPackage [-PackageId] <String> [-LogsDirectoryPath <String>] [-WprpFile <String>]
 [-ConnectedDevice]
```

### Path
```
Uninstall-ProvisioningPackage -PackagePath <String> [-LogsDirectoryPath <String>] [-WprpFile <String>]
 [-ConnectedDevice]
```

### Installed
```
Uninstall-ProvisioningPackage [-AllInstalledPackages] [-LogsDirectoryPath <String>] [-WprpFile <String>]
 [-ConnectedDevice]
```

### Metadata
```
Uninstall-ProvisioningPackage [-RuntimeMetadata] <RuntimeProvPackageMetadata> [-LogsDirectoryPath <String>]
 [-WprpFile <String>] [-ConnectedDevice]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -AllInstalledPackages
{{Fill AllInstalledPackages Description}}

```yaml
Type: SwitchParameter
Parameter Sets: Installed
Aliases: All

Required: True
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
{{Fill LogsDirectoryPath Description}}

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

### -PackageId
{{Fill PackageId Description}}

```yaml
Type: String
Parameter Sets: Id
Aliases: Id

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackagePath
{{Fill PackagePath Description}}

```yaml
Type: String
Parameter Sets: Path
Aliases: Path

Required: True
Position: Named
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

