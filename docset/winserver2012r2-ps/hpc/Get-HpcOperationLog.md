---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title:
description:
keywords: powershell, cmdlet
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: http://go.microsoft.com/fwlink/?LinkId=182659
schema: 2.0.0
title: Add-HpcDriver
ms.assetid: B0D29FB7-E5E3-466A-8247-05A7151F1734
manager: dansimp
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Get-HpcOperationLog

## SYNOPSIS
Gets the log and substeps for the specified operation.

## SYNTAX

```
Get-HpcOperationLog [-Operation] <HpcOperation> [-Severity <LogLevel[]>]
 [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcOperationLog** cmdlet gets the log and substeps for the specified operation.

## EXAMPLES

### Example 1: Get events for the oldest available operation
```
PS C:\>(Get-HpcOperation)[0] | Get-HpcOperationLog
```

This command gets the events in the event log for the oldest available operation for the HPC cluster.

### Example 2: Get events for multiple severity levels
```
PS C:\>Get-HpcOperation -State Reverted | Select-Object -Last 1 | Get-HpcOperationLog -Severity Error,Warning
```

This command gets the events with a severity level of Error or Warning from the event log for the last operation that was reverted.

## PARAMETERS

### -Operation
Specifies an **HpcOperation** object for the operation for which you want to get the log.
Use the Get-HpcOperation cmdlet to get an **HpcOperation** object for an operation.

```yaml
Type: HpcOperation
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster on which the operation ran.
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

### -Severity
Specifies an array of severity levels of the events that you want to get.
Use this parameter to retrieve error, warning, or informational messages from the log for the operation.
Valid values are:

- Error
- Warning
- Information

```yaml
Type: LogLevel[]
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

### HpcOperation

## OUTPUTS

### ChangeLogEntry[]

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcOperation](./Get-HpcOperation.md)

[Stop-HpcOperation](./Stop-HpcOperation.md)
