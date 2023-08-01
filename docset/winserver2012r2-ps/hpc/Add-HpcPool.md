---
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/add-hpcpool?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-HpcPool
---

# Add-HpcPool

## SYNOPSIS
Adds a resource pool to an HPC cluster.

## SYNTAX

```
Add-HpcPool -Name <String> [-Scheduler <String[]>] [-Weight <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-HpcPool** cmdlet adds a new resource pool on an HPC cluster.

## EXAMPLES

### Example 1: Add a resource pool to a scheduler
```
PS C:\>Add-HPCPool -Scheduler "HEADNODE" -Name "Pool01" -Weight 42
```

This command adds a resource pool to the scheduler on the head node with a weight of 42.

## PARAMETERS

### -Name
Specifies the name of the new resource pool.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster to which to add the resource pool.
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

### -Weight
Specifies the weight of the pool that to create on the HPC cluster.

The valid range of weight value is between 0 and 999999.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

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
* This cmdlet was introduced in HPC Pack 2008 R2 with Service Pack 2 (SP2). It is not supported in previous versions.

## RELATED LINKS

[Get-HpcPool](./Get-HpcPool.md)

[Remove-HpcPool](./Remove-HpcPool.md)

[Set-HpcPool](./Set-HpcPool.md)
