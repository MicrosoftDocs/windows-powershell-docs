---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/hyper-v/new-vmresourcepool?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-VMResourcePool
---

# New-VMResourcePool

## SYNOPSIS
Creates a resource pool.

## SYNTAX

```
New-VMResourcePool [-Name] <String> [-ResourcePoolType] <VMResourcePoolType[]> [[-ParentName] <String[]>]
 [[-Paths] <Object[]>] [-ComputerName <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-VMResourcePool** cmdlet creates a resource pool.

## EXAMPLES

### Example 1
```
PS C:\> New-VMResourcePool "New Resource Pool" VHD -Paths d:\VHDs
```

Creates a new virtual hard disk resource pool associated with a single path.

### Example 2
```
PS C:\> New-VMResourcePool "New Resource Pool" VHD  -Paths "d:\VHDs","e:\Temp"
```

Creates a new virtual hard disk resource pool associated with multiple paths.

### Example 3
```
PS C:\> New-VMResourcePool "New Resource Pool" Ethernet
```

Creates a new ethernet resource pool.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the resource pool is to be created.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the resource pool

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ParentName
Specifies the name of the parent resource pool for the new resource pool.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Paths
Specifies an array of paths to be associated with a new storage resource pool.

```yaml
Type: Object[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourcePoolType
Specifies the resource type of the resource pool.

```yaml
Type: VMResourcePoolType[]
Parameter Sets: (All)
Aliases: 
Accepted values: Memory, Processor, Ethernet, VHD, ISO, VFD, FibreChannelPort, FibreChannelConnection

Required: True
Position: 1
Default value: None
Accept pipeline input: False
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

### Microsoft.HyperV.PowerShell.ResourcePool

## NOTES

## RELATED LINKS

