---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Resume-VMReplication
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 6A875733-47A2-4480-8A88-05D2516599BC
---

# Resume-VMReplication

## SYNOPSIS
Resumes a virtual machine replication that is in a state of Paused, Error, Resynchronization Required, or Suspended.

## SYNTAX

### VMName (Default)
```
Resume-VMReplication [-ResynchronizeStartTime <DateTime>] [-Resynchronize] [-AsJob] [-Continue]
 [-ReplicationRelationshipType <VMReplicationRelationshipType>] [-ComputerName <String[]>] [-VMName] <String[]>
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Resume-VMReplication [-ResynchronizeStartTime <DateTime>] [-Resynchronize] [-AsJob] [-Continue]
 [-ReplicationRelationshipType <VMReplicationRelationshipType>] [-PassThru] [-VM] <VirtualMachine[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### VMReplication
```
Resume-VMReplication [-ResynchronizeStartTime <DateTime>] [-Resynchronize] [-AsJob] [-Continue]
 [-VMReplication] <VMReplication[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Resume-VMReplication** cmdlet resumes replication of a virtual machine with a replication state of Paused, Error, Resynchronization Required, or Suspended.

## EXAMPLES

### Example 1
```
PS C:\> Resume-VMReplication VM01
```

This example resumes replication of virtual machine VM01.

### Example 2
```
PS C:\> Resume-VMReplication VM01 -Resynchronize
```

This example resynchronizes replication of virtual machine VM01.

### Example 3
```
PS C:\> Resume-VMReplication VM01 -Resynchronize -ResynchronizeStartTime "8/1/2012 05:00 AM"
```

This example schedules the resynchronization of replication for virtual machine VM01 to start at 5:00 AM on August 1, 2012.

### Example 4
```
PS C:\> Resume-Replication *
```

This example resumes replication of all virtual machines for which replication is paused.

## PARAMETERS

### -AsJob
Specifies that the cmdlet is to be run as a background job.

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

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual machine replication is to be resumed.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName
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

### -Continue
Indicates that Hyper-V Replica continues the resynchronization comparisons from where it left off when you resume the virtual machine replication.

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

### -PassThru
Specifies that a **VMReplication** object is to be passed through to the pipeline representing the virtual machine replication to be resumed.

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

### -ReplicationRelationshipType
Specifies the replication relationship type of the virtual machine.
Specify whether the replication relationship is a simple primary to replica or is an extended replication chain.
The cmdlet resumes the replication of the virtual machines that have the replication type that you specify.

```yaml
Type: VMReplicationRelationshipType
Parameter Sets: VMName, VMObject
Aliases: Relationship
Accepted values: Simple, Extended

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Resynchronize
Specifies that resynchronization is to be started for the virtual machine.
Resynchronization requires significant storage, processor, and network resources.
We recommend running this process during off-peak hours.
Use the **Set-VMReplication** cmdlet to specify whether to automatically resynchronize the virtual machine in the future.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: Resync

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResynchronizeStartTime
Specifies when resynchronization should start.
If not specified, resynchronization starts immediately.
You can schedule the resynchronization to start up to 7 days later.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: ResyncStart

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine whose replication is to be resumed.

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine whose replication is to be resumed.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMReplication
Specifies a virtual machine replication object representing the virtual machine replication to be resumed.

```yaml
Type: VMReplication[]
Parameter Sets: VMReplication
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

###  
None by default; **VMReplication** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

