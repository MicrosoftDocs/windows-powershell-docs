---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/add-vmswitchextensionswitchfeature?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-VMSwitchExtensionSwitchFeature
---

# Add-VMSwitchExtensionSwitchFeature

## SYNOPSIS
Adds a feature to a virtual switch.

## SYNTAX

### SwitchName
```
Add-VMSwitchExtensionSwitchFeature [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] -VMSwitchExtensionFeature <VMSwitchExtensionSwitchFeature[]>
 [-SwitchName] <String[]> [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SwitchObject
```
Add-VMSwitchExtensionSwitchFeature -VMSwitchExtensionFeature <VMSwitchExtensionSwitchFeature[]>
 [-VMSwitch] <VMSwitch[]> [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-VMSwitchExtensionSwitchFeature** cmdlet adds a feature supported by a virtual switch extension to a virtual switch.

## EXAMPLES

### Example 1
```
PS C:\> $feature = Get-VMSwitchExtensionSwitchFeature -FeatureName "Ethernet Switch BandwidthSettings"
PS C:\> $feature.SettingData.DefaultFlowReservation = 300000000
PS C:\> Add-VMSwitchExtensionSwitchFeature "External" -VMSwitchExtensionSwitchFeature $feature
```

Adds a feature to virtual switch External.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: SwitchName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which a feature is to be added to a virtual switch.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

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

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: SwitchName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the feature to be added.

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
Specifies the name of the virtual switch to which the feature is to be added.

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
Specifies the virtual switch to which the feature is to be added.

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
Specifies the feature to be added to the virtual switch.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.HyperV.PowerShell.VMSwitchExtensionSwitchFeature
If **-PassThru** is specified.

## NOTES

## RELATED LINKS

