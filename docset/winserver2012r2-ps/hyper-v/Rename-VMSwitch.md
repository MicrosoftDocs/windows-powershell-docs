---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Rename-VMSwitch
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
ms.assetid: D153EEC8-80AB-4999-A054-8DDA38BCC0FA
---

# Rename-VMSwitch

## SYNOPSIS
Renames a virtual switch.

## SYNTAX

### SwitchName (Default)
```
Rename-VMSwitch [-ComputerName <String[]>] [-Name] <String> [-NewName] <String> [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SwitchObject
```
Rename-VMSwitch [-VMSwitch] <VMSwitch> [-NewName] <String> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Rename-VMSwitch** cmdlet renames a virtual switch.

## EXAMPLES

### Example 1
```
PS C:\>Rename-VMSwitch "QoS Switch" -NewName "IIS Switch"
```

Renames virtual switch QoS Switch as IIS Switch.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual switch is to be renamed.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: SwitchName
Aliases: 

Required: False
Position: Named
Default value: .
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

### -Name
Specifies the name of the virtual switch to be renamed.

```yaml
Type: String
Parameter Sets: SwitchName
Aliases: SwitchName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NewName
Specifies the name to which the virtual switch is to be renamed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.EthernetSwitch** object is to be passed through to the pipeline representing the virtual switch to be renamed.

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

### -VMSwitch
Specifies the virtual switch to be renamed.

```yaml
Type: VMSwitch
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

###  
None by default; **Microsoft.HyperV.PowerShell.EthernetSwitch** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

