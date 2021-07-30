---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/remove-hpcpool?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-HpcPool
---

# Remove-HpcPool

## SYNOPSIS
Removes a resource pool.

## SYNTAX

### pool (Default)
```
Remove-HpcPool -Pool <HpcPool> [-Force] [-Scheduler <String[]>]
 [<CommonParameters>]
```

### name
```
Remove-HpcPool -Name <String> [-Force] [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HpcPool** cmdlet removes the specified resource pool.
Returns an error if the pool is used in one or more templates.
You can use the *Force* parameter to force removal of the pools, which resets the template or templates to use the default pool.

## EXAMPLES

### Example 1: Remove a resource pool by name
```
PS C:\>Remove-HpcPool -Scheduler "HeadNode" -Name "Pool01"
```

This command removes a resource pool using the name of the head node and the name of the pool that you want to remove:

## PARAMETERS

### -Force
Indicates that this operation forces the removal of the specified pool.
This parameter resets the template or templates to use the default pool.

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

### -Name
Specifies the name of the pool on the cluster to be deleted.
You cannot specify both the *Name* and the *Pool* parameters.

```yaml
Type: String
Parameter Sets: name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pool
Specifies the **HpcPool** object to remove.
You cannot specify both the *Name* and the *Pool* parameters.

```yaml
Type: HpcPool
Parameter Sets: pool
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node that contains the resource pool.
The value must be a valid computer name or IP address.
If you do not specify the *Scheduler* parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.
To set this environment variable, run the following cmdlet:

`Set-Content Env:CCP_SCHEDULER \<head_node_name\>`

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
* This cmdlet was introduced in HPC Pack 2008 R2 with Service Pack 2 (SP2). It is not supported in previous versions.

## RELATED LINKS

[Add-HpcPool](./Add-HpcPool.md)

[Get-HpcPool](./Get-HpcPool.md)

[Set-HpcPool](./Set-HpcPool.md)
