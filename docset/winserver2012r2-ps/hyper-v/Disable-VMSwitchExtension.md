---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Disable-VMSwitchExtension
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: A0007E5F-FABE-4E1C-8EB2-79D062639F93
---

# Disable-VMSwitchExtension

## SYNOPSIS
Disables one or more extensions on one or more virtual switches.

## SYNTAX

### ExtensionName (Default)
```
Disable-VMSwitchExtension [-ComputerName <String[]>] [-Name] <String[]> [<CommonParameters>]
```

### ExtensionNameSwitchName
```
Disable-VMSwitchExtension [-ComputerName <String[]>] [-Name] <String[]> [-VMSwitchName] <String[]>
 [<CommonParameters>]
```

### ExtensionNameSwitchObject
```
Disable-VMSwitchExtension [-Name] <String[]> [-VMSwitch] <VMSwitch[]> [<CommonParameters>]
```

### ExtensionObject
```
Disable-VMSwitchExtension [-VMSwitchExtension] <VMSwitchExtension[]> [<CommonParameters>]
```

## DESCRIPTION
The **Disable-VMSwitchExtension** cmdlet disables one or more extensions on one or more virtual switches.
You can run Get-VMSystemSwitchExtension to enumerate the virtual switch extensions installed on the system.

## EXAMPLES

### Example 1
```
PS C:\>Disable-VMSwitchExtension -VMSwitchName "Internal Switch" -Name "Microsoft Windows Filtering Platform"
```

Disables WFP ("Microsoft Windows Filtering Platform") on virtual switch Internal Switch.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the extension is to be disabled.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: ExtensionName, ExtensionNameSwitchName
Aliases: PSComputerName

Required: False
Position: Named
Default value: .
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the extension to be disabled.

```yaml
Type: String[]
Parameter Sets: ExtensionName, ExtensionNameSwitchName, ExtensionNameSwitchObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSwitch
Specifies the virtual switch on which the extension is to be disabled.

```yaml
Type: VMSwitch[]
Parameter Sets: ExtensionNameSwitchObject
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMSwitchExtension
Specifies the extension to be disabled.

```yaml
Type: VMSwitchExtension[]
Parameter Sets: ExtensionObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMSwitchName
Specifies the name of the switch on which the extension is to be disabled.

```yaml
Type: String[]
Parameter Sets: ExtensionNameSwitchName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.NetworkExtension

## NOTES

## RELATED LINKS

