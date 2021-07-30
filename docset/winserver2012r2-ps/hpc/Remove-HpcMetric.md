---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/remove-hpcmetric?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-HpcMetric
---

# Remove-HpcMetric

## SYNOPSIS
Removes metrics from the set of metrics that HPC Cluster Manager uses in the heat maps for the nodes and the monitoring charts.

## SYNTAX

```
Remove-HpcMetric [-Name] <String[]> [-Scheduler <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HpcMetric** cmdlet removes one or more specified metrics from the set of metrics that HPC Cluster Manager uses in the heat maps for the nodes and the monitoring charts.

## EXAMPLES

### Example 1: Remove a metric by name
```
PS C:\>Remove-HpcMetric -Name "MyCustomMetric"
```

This command removes the metric named MyCustomMetric.

### Example 2: Remove metrics for a head node
```
PS C:\>Remove-HpcMetric -Name "CustomMetric1,CustomMetric2" -Scheduler "HeadNode"
```

This command removes the metrics named CustomMetric1 and CustomMetric2 from the HPC cluster that has a head node named HeadNode.

### Example 3: Get metrics by category and remove them
```
PS C:\>Get-HpcMetric -Type "Calculated" | Remove-HpcMetric
```

This command gets **HpcMetric** objects for all of the metrics with a category of Calculated, and then removes those metrics.

## PARAMETERS

### -Name
Specifies an array of the names of metrics that you want to remove.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the metrics.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcMetric[]

## OUTPUTS

### None

## NOTES
* The built-in ConfirmImpact setting for this cmdlet is Medium. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify `-Confirm:$False`. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify `-Confirm` or `-Confirm:$True`.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcMetric](./Get-HpcMetric.md)

[Import-HpcMetric](./Import-HpcMetric.md)
