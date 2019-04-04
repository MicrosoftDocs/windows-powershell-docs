---
author: kenwith
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: provcmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.author: kenwith
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
{{Fill in the Synopsis}}

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
Position: 0
Default value: None
Accept pipeline input: False
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

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

