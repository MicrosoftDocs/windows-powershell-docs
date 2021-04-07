---
author: Kateyanne
description: 
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
manager: jasgro
Module Name: Hyper-V
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/hyper-v/remove-vmswitchextensionswitchfeature?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VMSwitchExtensionSwitchFeature
---

# Remove-VMSwitchExtensionSwitchFeature

## SYNOPSIS
Removes a feature from a virtual switch.

## SYNTAX

### SwitchName
```
Remove-VMSwitchExtensionSwitchFeature [-ComputerName <String[]>] [-SwitchName] <String[]>
 -VMSwitchExtensionFeature <VMSwitchExtensionSwitchFeature[]> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SwitchObject
```
Remove-VMSwitchExtensionSwitchFeature [-VMSwitch] <VMSwitch[]>
 -VMSwitchExtensionFeature <VMSwitchExtensionSwitchFeature[]> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VMSwitchExtensionSwitchFeature** removes a feature from a virtual switch.
The feature already must have been configured on the virtual switch.

## EXAMPLES

### Example 1
```
PS C:\>$feature = Get-VMSwitchExtensionSwitchFeature -SwitchName External -FeatureId 3eb2b8e8-4abf-4dbf-9071-16dd47481fbe
PS C:\>Remove-VMSwitchExtensionSwitchFeature External $feature
```

Removes a feature from virtual switch External.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which the feature is to be removed.
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.VMSwitchExtensionSwitchFeature** is to be passed through to the pipeline representing the feature to be removed.

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
Specifies the name of the virtual switch from which the feature is to be removed.

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
Specifies the virtual switch from which the feature is to be removed.

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

### -VMSwitchExtensionFeature
Specifies the feature to be removed.

```yaml
Type: VMSwitchExtensionSwitchFeature[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
None by default; **Microsoft.HyperV.PowerShell.VMSwitchExtensionSwitchFeature** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

