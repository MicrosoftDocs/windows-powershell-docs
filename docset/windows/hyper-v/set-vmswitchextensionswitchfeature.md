---
author: brianlic-msft
description: 
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-VMSwitchExtensionSwitchFeature
ms.assetid: 4CA92606-3CA4-4197-B5DA-3E609D5F4851
---

# Set-VMSwitchExtensionSwitchFeature

## SYNOPSIS
Configures a feature on a virtual switch.

## SYNTAX

```
Set-VMSwitchExtensionSwitchFeature -VMSwitchExtensionFeature <VMSwitchExtensionSwitchFeature[]> [-Passthru]
 [-ComputerName <String[]>] [-SwitchName <String[]>] [-VMSwitch <VMSwitch[]>] [-CimSession <CimSession[]>]
 [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMSwitchExtensionSwitchFeature** cmdlet configures a feature on a virtual switch.
The feature must have already been configured on the virtual switch.

## EXAMPLES

### Example 1
```
PS C:\>$feature = Get-VMSystemSwitchExtensionSwitchFeature -FeatureName "Ethernet Switch Bandwidth Settings"
PS C:\>$feature.SettingData.DefaultFlowReservation = 100000000
PS C:\>Set-VMSwitchExtensionSwitchFeature External $feature
```

Configures the feature on virtual switch External.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which this cmdlet operates.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.VMSwitchExtensionSwitchFeature** is to be passed through to the pipeline representing the feature to be configured.

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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSwitch
Specifies the virtual switch.

```yaml
Type: VMSwitch[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSwitchExtensionFeature
Specifies the feature to be configured.

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

