---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/get-hpcnodestatehistory?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HpcNodeStateHistory
---

# Get-HpcNodeStateHistory

## SYNOPSIS
Gets the history of changes to the state of the nodes in the HPC cluster for the specified time period.

## SYNTAX

### AllNode (Default)
```
Get-HpcNodeStateHistory [-StartDate] <DateTime> [-EndDate] <DateTime>
[-Scheduler <String[]>] [<CommonParameters>]
```

### Name
```
Get-HpcNodeStateHistory [-StartDate] <DateTime> [-EndDate] <DateTime> [-Name <String[]>]
 [-Scheduler <String[]>] [<CommonParameters>]
```

### Node
```
Get-HpcNodeStateHistory [-StartDate] <DateTime> [-EndDate] <DateTime> [-Node <HpcNode[]>] [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcNodeStateHistory** cmdlet gets the history of changes to the state of the nodes in the HPC cluster for the specified time period.
The time period is the period after the specified start date and time and before the specified end date and time.

You can schedule this cmdlet to run daily and export the history of node states to a database.
You can then use this database to track node availability.

## EXAMPLES

### Example 1: Get the history of node state changes
```
PS C:\>Get-HpcNodeStateHistory -StartDate (Get-Date).AddDays(-1) -EndDate (Get-Date)
```

This command gets the history of changes to the node state for the previous day.
Run this cmdlet daily at midnight or other appropriate time to update the database you use to track node availability.

## PARAMETERS

### -EndDate
Specifies a **DateTime** object for the end date and time for the time period for which you want to get the history of changes to the node states.
Use the Get-Date cmdlet to get a **DateTime** object for a date and time.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of names for the nodes for which you want to retrieve the history of changes.
You cannot specify both the *Name* and *Node* parameters.

This parameter was introduced in HPC Pack 2012.
It is not supported in previous versions.

```yaml
Type: String[]
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Node
Specifies an array of **HpcNode** objects for the nodes for which you want to get the history of changes.
You cannot specify both the *Name* and *Node* parameters.

This parameter was introduced in HPC Pack 2012.
It is not supported in previous versions.

```yaml
Type: HpcNode[]
Parameter Sets: Node
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster for which you want to get the history of changes to the state of the nodes.
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

### -StartDate
Specifies a **DateTime** object for the start date and time for the time period for which you want to get the history of changes to the node states.
Use the Get-Date cmdlet to get a **DateTime** object for a date and time.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### HpcNodeHistory

## NOTES
* The time stamps in the history of node states are in the time zone of the local computer instead of the time zone of the head node for the cluster. Run this cmdlet on a computer located in the same time zone as head node to get consistent results.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcJobHistory](./Get-HpcJobHistory.md)
