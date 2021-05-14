---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/set-vmresourcepool?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-VMResourcePool

## SYNOPSIS
Sets the parent resource pool for a selected resource pool.

## SYNTAX

```
Set-VMResourcePool [-Name] <String[]> [-ResourcePoolType] <VMResourcePoolType> [-ParentName] <String[]>
 [-ComputerName <String[]>] [-Passthru] [-Confirm] [-WhatIf]
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

### -Name
Specifies the resource pool whose parent resource pool is to be set.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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
Position: 3
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

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### None
Default

### VMResourcePool
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



