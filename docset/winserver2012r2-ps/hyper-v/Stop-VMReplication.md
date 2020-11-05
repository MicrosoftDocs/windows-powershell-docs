---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Stop-VMReplication
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
ms.assetid: E9A22187-E371-4CCA-8EDC-506354BDCC74
---

# Stop-VMReplication

## SYNOPSIS
Cancels an ongoing virtual machine resynchronization.

## SYNTAX

### VMName (Default)
```
Stop-VMReplication [-ReplicationRelationshipType <VMReplicationRelationshipType>] [-ComputerName <String[]>]
 [-VMName] <String[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Stop-VMReplication [-ReplicationRelationshipType <VMReplicationRelationshipType>] [-PassThru]
 [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMReplication
```
Stop-VMReplication [-VMReplication] <VMReplication[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-VMReplication** cmdlet cancels an ongoing virtual machine resynchronization.

## EXAMPLES

### Example 1
```
PS C:\>Stop-VMReplication *
```

Stops all ongoing replications of virtual machines on the local Hyper-V server.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the ongoing virtual machine resynchronization is to be stopped.
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

### -PassThru
Specifies that an object is to be passed through to the pipeline representing the virtual machine on which the ongoing virtual machine resynchronization is to be stopped.

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
The cmdlet cancels the ongoing resynchronization of the virtual machines that have the replication type that you specify.

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

### -VM
Specifies the virtual machine whose resynchronization is to be stopped.

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
Specifies the name of the virtual machine whose resynchronization is to be stopped.

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
Specifies the resynchronization to be stopped.

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
None by default; **Microsoft.HyperV.PowerShell.VirtualMachine** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

