---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/hyper-v/measure-vmreplication?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-VMReplication
---

# Measure-VMReplication

## SYNOPSIS
Gets replication statistics and information associated with a virtual machine.

## SYNTAX

### VMName (Default)
```
Measure-VMReplication [-ComputerName <String[]>] [[-VMName] <String[]>] [-ReplicaServerName <String>]
 [-PrimaryServerName <String>] [-ReplicationState <VMReplicationState>]
 [-ReplicationHealth <VMReplicationHealthState>] [-ReplicationMode <VMReplicationMode>]
 [-ReplicationRelationshipType <VMReplicationRelationshipType>] [-TrustGroup <String>] [<CommonParameters>]
```

### VMObject
```
Measure-VMReplication [-ReplicationRelationshipType <VMReplicationRelationshipType>] [-VM] <VirtualMachine[]>
 [<CommonParameters>]
```

## DESCRIPTION
The **Measure-VMReplication** cmdlet gets replication statistics and information associated with virtual machine.
Replication statistics are calculated for a predetermined amount of time based on the monitoring interval specified through the Set-VMReplicationServer cmdlet.

## EXAMPLES

### Example 1
```
PS C:\> Measure-VMReplication
```

This example gets the replication monitoring details of all replicating virtual machines on the local host.

### Example 2
```
PS C:\> Measure-VMReplication VM01
```

This example gets the replication monitoring details of a virtual machine named VM01.

### Example 3
```
PS C:\>  Measure-VMReplication -ReplicationHealth Warning
```

This example gets the replication monitoring details of all virtual machines that have a replication health of "Warning".

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which to get replication statistics.
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
Specifies the name of a primary server.
Replication statistics are retrieved for all virtual machines from the specified primary server.

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
Specifies the name of a Replica server of the virtual machines whose replication statistics you want to get.

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
Specifies the replication health of the virtual machines whose replication statistics you want to get.
Valid values are "Critical", "Warning", "Normal", and "NotApplicable".

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
Specifies the replication mode of the virtual machines whose replication statistics you want to get.
Valid values are "None", "Primary", "Replica" and "TestReplica".

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
The cmdlet gets replication statistics and information associated with the virtual machines that have the replication type that you specify.

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
Specifies the replication state of the virtual machines for which you want to get replication statistics.
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
Specifies a trust group associated with the virtual machines whose replication statistics you want to get.

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
Specifies the virtual machine for which you want to get replication statistics.

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
Specifies the name of the virtual machine for which you want to get virtual machine replication statistics.

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

### VMReplicationHealth

## NOTES

## RELATED LINKS

