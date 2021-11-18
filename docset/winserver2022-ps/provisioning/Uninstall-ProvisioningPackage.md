---
description: The Uninstall-ProvisioningPackage cmdlet uninstalls .ppkg files.
external help file: provcmdlets.dll-Help.xml
Module Name: Provisioning
ms.date: 05/09/2017
online version: https://docs.microsoft.com/powershell/module/provisioning/uninstall-provisioningpackage?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-ProvisioningPackage
---

# Uninstall-ProvisioningPackage

## SYNOPSIS
Uninstalls .ppkg files.

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
The **Uninstall-ProvisioningPackage** cmdlet uninstalls .ppkg files.

The **Uninstall-ProvisioningPackage** cmdlet is supported on Windows 11 client operating system only.

## EXAMPLES

### Example 1: Uninstall a package
```
Uninstall-ProvisioningPackage -PackagePath C:\mypackage.ppkg
```

This example uninstalls a package with the specified path.

## PARAMETERS

### -AllInstalledPackages
Indicates that the cmdlet uninstalls all installed packages.

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
Specifies a path to store logs files resulting from the operation.

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
Specifies the ID of the Package to be uninstalled.

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
Specifies the path to the package to be uninstalled.

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

