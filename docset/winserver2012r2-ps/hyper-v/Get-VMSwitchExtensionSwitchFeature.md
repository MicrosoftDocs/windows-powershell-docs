---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Get-VMSwitchExtensionSwitchFeature
ms.author: v-anbarr
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: D82ECE6C-2741-45E4-9A96-3FFDFC1CC093
---

# Get-VMSwitchExtensionSwitchFeature

## SYNOPSIS
Gets the features configured on a virtual switch.

## SYNTAX

### SwitchName
```
Get-VMSwitchExtensionSwitchFeature [-FeatureName <String[]>] [-FeatureId <Guid[]>]
 [-Extension <VMSwitchExtension[]>] [-ExtensionName <String[]>] [-ComputerName <String[]>]
 [-SwitchName] <String[]> [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SwitchObject
```
Get-VMSwitchExtensionSwitchFeature [-FeatureName <String[]>] [-FeatureId <Guid[]>]
 [-Extension <VMSwitchExtension[]>] [-ExtensionName <String[]>] [-VMSwitch] <VMSwitch[]> [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMSwitchExtensionSwitchFeature** cmdlet gets the features configured on a virtual switch.
The object can be used to update the configuration of the switch using the Set-VmSwitchExtensionFeature command.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMSwitchExtensionSwitchFeature -SwitchName MySwitch
```

The following command returns all the configured features on the switch named MySwitch.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the features configured on a virtual switch are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: SwitchName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Extension
Specifies the virtual switch extension.

```yaml
Type: VMSwitchExtension[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtensionName
Specifies the name of the virtual switch extension.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FeatureId
Specifies the unique identifier of the feature.

```yaml
Type: Guid[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FeatureName
Specifies the name of the feature.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.VMSwitchExtensionSwitchFeature** object is to be passed through to the pipeline representing the features to be retrieved.

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

### -SwitchName
Specifies the name of the virtual switch.

```yaml
Type: String[]
Parameter Sets: SwitchName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMSwitch
Specifies the virtual switch.

```yaml
Type: VMSwitch[]
Parameter Sets: SwitchObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

