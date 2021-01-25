---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Set-VMResourcePool
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 13E11B15-29AF-4D7F-A96A-10E4ECC4324E
---

# Set-VMResourcePool

## SYNOPSIS
Sets the parent resource pool for a selected resource pool.

## SYNTAX

```
Set-VMResourcePool [-ComputerName <String[]>] [-Name] <String[]> [-ResourcePoolType] <VMResourcePoolType>
 [-ParentName] <String[]> [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMResourcePool** cmdlet sets a parent resource pool for a selected resource pool.
(To remove a parent from a resource pool, set the primordial pool of the resource pool's type as its parent.)

## EXAMPLES

### Example 1
```
PS C:\>Set-VMResourcePool ChildPool VHD ParentPool
```

Set a virtual hard drive resource pool ParentPool as the parent of virtual hard drive resource pool ChildPool.

### Example 2
```
PS C:\>Set-VMResourcePool ChildPool VHD Primordial
```

Remove the parent resource pool from virtual hard drive resource pool ChildPool.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which a resource pool's parent is to be set.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: True (ByPropertyName)
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

### -Name
Specifies the resource pool whose parent resource pool is to be set.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ParentName
Specifies the name of the resource pool to be set as a parent.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **VMResourcePool** object is to be passed through to the pipeline representing the resource pool whose parent is to be set.

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

### -ResourcePoolType
Specifies the type of the resource pool whose parent is to be set.

```yaml
Type: VMResourcePoolType
Parameter Sets: (All)
Aliases: 
Accepted values: Memory, Processor, Ethernet, VHD, ISO, VFD, FibreChannelPort, FibreChannelConnection

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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
None by default; **VMResourcePool** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

