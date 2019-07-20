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
title: Install-ProvisioningPackage
ms.reviewer:
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

You can direct this cmdlet to install a PPKG file interactively or silently by specifying the -QuietInstall Switch.

The default is an interactive install.

## EXAMPLES

### Example 1
```
PS C:\> Install-ProvisioningPackage -PackagePath C:\mypackage.ppkg -QuietInstall  
```

The snippet above will install the mypackage.ppkg file quietly without user interaction.

## PARAMETERS

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

### -ForceInstall
{{Fill ForceInstall Description}}

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
Quietly installs the package with no end user interaction

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

