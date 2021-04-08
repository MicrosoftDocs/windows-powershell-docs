---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/new-vmresourcepool?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-VMResourcePool

## SYNOPSIS
Creates a resource pool.

## SYNTAX

```
New-VMResourcePool [-Name] <String> [-ResourcePoolType] <VMResourcePoolType[]> [[-ParentName] <String[]>]
 [[-Paths] <Object[]>] [-ComputerName <String[]>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **New-VMResourcePool** cmdlet creates a resource pool.

## EXAMPLES

### Example 1
```
PS C:\>New-VMResourcePool "New Resource Pool" VHD -Paths d:\VHDs
```

Creates a new virtual hard disk resource pool with associated with a single path.

### Example 2
```
PS C:\>New-VMResourcePool "New Resource Pool" VHD  -Paths "d:\VHDs","e:\Temp"
```

Creates a new virtual hard disk resrouce pool associated with multiple paths.

### Example 3
```
PS C:\>New-VMResourcePool "New Resource Pool" Ethernet
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

### -Name
Specifies the name of the resource pool

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Paths
Specifies an array of paths to be associated with a new storage resource pool.

```yaml
Type: Object[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
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

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Virtualization.Powershell.ResourcePool

## NOTES

## RELATED LINKS



