---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: provcmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.author: v-anbarr
ms.date: 2017-05-09
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-ProvisioningPackage
ms.reviewer:
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
Specifies the name of a wprp file.

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

