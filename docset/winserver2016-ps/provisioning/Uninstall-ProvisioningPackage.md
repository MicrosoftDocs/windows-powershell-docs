---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: provcmdlets.dll-Help.xml
Module Name: Provisioning
ms.date: 05/09/2017
online version: https://docs.microsoft.com/powershell/module/provisioning/uninstall-provisioningpackage?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-ProvisioningPackage
---

# Uninstall-ProvisioningPackage

## SYNOPSIS
Uninstalls .PPKG package from the local machine

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
Unintalls .PPKG package based on package id, path, metadata or all packages.

## EXAMPLES

### Example 1: Uninstall all provisioning packages
```powershell
PS C:\> Uninstall-ProvisioningPackage -AllInstalledPackages
```

Uninstalls all provisioning packages.

## PARAMETERS

### -AllInstalledPackages
Remove all installed packages.

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
If enabled specifies that device type is mobile.

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
Specifies the logs directory path.

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
Specifies the Id of a package.

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
Specifies the package path.

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
Specifies the location of the WPR profile file.

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

