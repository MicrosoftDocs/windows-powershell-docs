---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Get-VMReplication
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: C8DB44FD-2CE3-499A-9232-576370E1517C
---

# Get-VMReplication

## SYNOPSIS
Gets the replication settings for a virtual machine.

## SYNTAX

### VMName (Default)
```
Get-VMReplication [-ComputerName <String[]>] [[-VMName] <String[]>] [-ReplicaServerName <String>]
 [-PrimaryServerName <String>] [-ReplicationState <VMReplicationState>]
 [-ReplicationHealth <VMReplicationHealthState>] [-ReplicationMode <VMReplicationMode>]
 [-ReplicationRelationshipType <VMReplicationRelationshipType>] [-TrustGroup <String>] [<CommonParameters>]
```

### VMObject
```
Get-VMReplication [-ReplicationRelationshipType <VMReplicationRelationshipType>] [-VM] <VirtualMachine[]>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMReplication** cmdlet gets the replication settings for a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMReplication
```

This example gets the replication settings of all replication-enabled virtual machines on the local Hyper-V host.

### Example 2
```
PS C:\> Get-VMReplication VM01
```

This example gets the replication settings of a virtual machine named VM01.

### Example 3
```
PS C:\> Get-VMReplication -ReplicaServerName server01.domain01.contoso.com
```

This example gets the replication settings of all virtual machines replicating to server server01.domain01.contoso.com.

### Example 4
```
PS C:\> Get-VMReplication -ReplicationState Replicating
```

This example gets the replication settings of all virtual machines in the Replicating state.

### Example 5
```
PS C:\> Get-VMReplication -TrustGroup DEFAULT
```

This example gets the replication settings of all virtual machines in a trust group named DEFAULT.

### Example 6
```
PS C:\> Get-VMReplication -ReplicationMode Primary
```

This example gets the replication settings of all primary virtual machines on the local host.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which virtual machine replication settings are to be retrieved.
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

### -PrimaryServerName
Specifies the primary server of the virtual machines whose replication settings are to be retrieved.

```yaml
Type: String
Parameter Sets: VMName
Aliases: PrimaryServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicaServerName
Specifies the replica server name of the virtual machines whose replication settings are to be retrieved.

```yaml
Type: String
Parameter Sets: VMName
Aliases: ReplicaServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicationHealth
Gets replication settings for virtual machines with the specified replication health state.
Valid values are Normal, Warning, and Critical.

```yaml
Type: VMReplicationHealthState
Parameter Sets: VMName
Aliases: Health
Accepted values: NotApplicable, Normal, Warning, Critical

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicationMode
Gets the replication settings for virtual machines with the specified replication mode.
Valid values are None, Primary, Replica, and TestReplica.

```yaml
Type: VMReplicationMode
Parameter Sets: VMName
Aliases: Mode
Accepted values: None, Primary, Replica, TestReplica, ExtendedReplica

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicationRelationshipType
Specifies the replication relationship type of the virtual machine.
Specify whether the replication relationship is a simple primary to replica or is an extended replication chain.
The cmdlet gets the replication settings for the virtual machines that have the replication type that you specify.

```yaml
Type: VMReplicationRelationshipType
Parameter Sets: (All)
Aliases: Relationship
Accepted values: Simple, Extended

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicationState
Gets replication settings for virtual machines with the specified replication state.
Valid values are:

- Error
- FailOverWaitingCompletion
- FailedOver
- NotApplicable
- ReadyForInitialReplication
- Replicating
- Resynchronizing
- ResynchronizeSuspended
- Suspended
- SyncedReplicationComplete
- WaitingForInitialReplication
- WaitingForStartResynchronize

```yaml
Type: VMReplicationState
Parameter Sets: VMName
Aliases: State
Accepted values: Disabled, ReadyForInitialReplication, InitialReplicationInProgress, WaitingForInitialReplication, Replicating, PreparedForFailover, FailedOverWaitingCompletion, FailedOver, Suspended, Error, WaitingForStartResynchronize, Resynchronizing, ResynchronizeSuspended, RecoveryInProgress, FailbackInProgress, FailbackComplete

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrustGroup
Specifies the trust group of the virtual machines whose replication settings you want to retrieve.

```yaml
Type: String
Parameter Sets: VMName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine whose replication settings are to be retrieved.

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
Specifies the name of the virtual machine whose replication settings are to be retrieved.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: Name

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VMReplication

## NOTES

## RELATED LINKS

