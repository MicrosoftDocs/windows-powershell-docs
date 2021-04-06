---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: provcmdlets.dll-Help.xml
manager: jasgro
Module Name: provisioning
ms.author: v-kaunu
ms.date: 05/09/2017
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/provisioning/install-provisioningpackage?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-ProvisioningPackage
---

# Install-ProvisioningPackage

## SYNOPSIS
Install .PPKG package onto the local machine.

## SYNTAX

```
Install-ProvisioningPackage [-PackagePath] <String> [-ForceInstall] [-QuietInstall]
 [-LogsDirectoryPath <String>] [-WprpFile <String>] [-ConnectedDevice]
```

## DESCRIPTION
This cmdlet is used to install .ppkg files that are generated and exported by the [Windows Configuration Designer tool](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd).

You can use this cmdlet to install a .ppkg file interactively or silently by specifying the -QuietInstall switch parameter.

The default is an interactive install.

## EXAMPLES

### Example 1
```
PS C:\> Install-ProvisioningPackage -PackagePath C:\mypackage.ppkg -QuietInstall  
```

This will install the mypackage.ppkg file silently without customer interaction.

## PARAMETERS

### -ConnectedDevice
Install package to removable media.

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

### -ForceInstall
Force the installation of the package.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: Force

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

### -PackagePath
Path to provisioning package

```yaml
Type: String
Parameter Sets: (All)
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QuietInstall
Quietly installs the package without any customer interaction.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: Quiet

Required: False
Position: Named
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

