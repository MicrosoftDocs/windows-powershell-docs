---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Stop-HpcOperation
description:
keywords: powershell, cmdlet
ms.date: 12/20/2016
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: http://go.microsoft.com/fwlink/?LinkId=182659
schema: 2.0.0
ms.assetid: B0D29FB7-E5E3-466A-8247-05A7151F1734
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Stop-HpcOperation

## SYNOPSIS
Cancels the specified operation and makes the best possible attempt to revert the operation, if the operation is still running.

## SYNTAX

```
Stop-HpcOperation [-Operation] <HpcOperation>  [-Scheduler <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-HpcOperation** cmdlet cancels the specified operation and makes the best possible attempt to revert the operation, if the operation is still running.

## EXAMPLES

### Example 1: Get an operation and stop it
```
PS C:\>Get-HpcOperation -State Executing -Name "Performing maintenance on node CONTOSO\ComputeNode02." | Stop-HpcOperation
```

This command gets the **HpcOperation** object for the operation named "Performing maintenance on node CONTOSO\ComputeNode02." and that is in the Executing state, and cancels the operation by redirecting the **HpcOperation** object to the **Stop-HpcOperation** cmdlet.

## PARAMETERS

### -Operation
Specifies an **HpcOperation** object for the operation that you want to cancel.
Use the Get-HpcOperation cmdlet to get the **HpcOperation** object for the operation.

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
Specifies the host name or IP address of the head node for the cluster on which the operation is running.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcOperation

## OUTPUTS

### None

## NOTES
* The built-in ConfirmImpact setting for this cmdlet is Medium. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify `-Confirm:$False`. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify `-Confirm` or `-Confirm:$True`.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcOperation](./Get-HpcOperation.md)

[Get-HpcOperationLog](./Get-HpcOperationLog.md)
