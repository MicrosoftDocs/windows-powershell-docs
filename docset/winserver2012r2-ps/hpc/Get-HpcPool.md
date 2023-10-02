---
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/get-hpcpool?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HpcPool
---

# Get-HpcPool

## SYNOPSIS
Gets a resource pool.

## SYNTAX

```
Get-HpcPool [-Name <String>] [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcPool** cmdlet gets the resource pool specified by the *Name* parameter.
If no pool exists with the name specified, an error results.
If no pool name is specified, all available pools are returned.

## EXAMPLES

### Example 1: Get a resource pool by name
```
PS C:\>$Pool = Get-HpcPool -Scheduler "HEADNODE" -Name "Default"
```

This command gets property information for a specific resource pool that is on the cluster:

### Example 2: Get all resource pools in a cluster
```
PS C:\>$Pool = Get-HpcPool -Scheduler "HEADNODE"
```

This command gets property information for all of the resource pools that are on the cluster:

## PARAMETERS

### -Name
Specifies the name of the pool on the cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster where the specified pool resides.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
* This cmdlet was introduced in HPC Pack 2008 R2 with Service Pack 2 (SP2). It is not supported in previous versions.

## RELATED LINKS

[Add-HpcPool](./Add-HpcPool.md)

[Remove-HpcPool](./Remove-HpcPool.md)

[Set-HpcPool](./Set-HpcPool.md)
