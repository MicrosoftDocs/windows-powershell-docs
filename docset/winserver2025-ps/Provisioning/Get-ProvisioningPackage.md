---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: provcmdlets.dll-Help.xml
Module Name: Provisioning
ms.date: 05/09/2017
online version: https://learn.microsoft.com/powershell/module/provisioning/get-provisioningpackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ProvisioningPackage
---

# Get-ProvisioningPackage

## SYNOPSIS
Gets information about the installed provisioning package.

## SYNTAX

### Id
```
Get-ProvisioningPackage [-PackageId] <String> [-LogsDirectoryPath <String>] [-WprpFile <String>]
 [-ConnectedDevice]
```

### Path
```
Get-ProvisioningPackage [-PackagePath] <String> [-LogsDirectoryPath <String>] [-WprpFile <String>]
 [-ConnectedDevice]
```

### Installed
```
Get-ProvisioningPackage [-AllInstalledPackages] [-LogsDirectoryPath <String>] [-WprpFile <String>]
 [-ConnectedDevice]
```

## DESCRIPTION
The **Get-ProvisioningPackage** cmdlet gets information about the installed provisioning package.

The **Get-ProvisioningPackage** cmdlet is supported on Windows 11 client operating system only.

## EXAMPLES

### Example 1
```
PS C:\> Get-ProvisioningPackage -PackagePath c:\test\testppkg.ppkg
```

This command gets information about the testppkg.ppkg provisioning package.

## PARAMETERS

### -AllInstalledPackages

Gets all the installed packages information.

```yaml
Type: SwitchParameter
Parameter Sets: Installed
Aliases: All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectedDevice
Gets the connected device information.

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
Position: 0
Default value: None
Accept pipeline input: False
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

### None


## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

