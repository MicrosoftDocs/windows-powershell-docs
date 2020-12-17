---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Measure-VMReplication

## SYNOPSIS
Gets replication statistics and information associated with a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Measure-VMReplication [[-VMName] <String[]>] [-ComputerName <String[]>] [-PrimaryServerName <String>]
 [-ReplicaServerName <String>] [-ReplicationHealth <VMReplicationHealthState>]
 [-ReplicationMode <VMReplicationMode>] [-ReplicationState <VMReplicationState>] [-TrustGroup <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Measure-VMReplication [-VM] <VirtualMachine[]>
```

## DESCRIPTION
The **Measure-VMReplication** cmdlet gets replication statistics and information associated with virtual machine.
Replication statistics are calculated for a predetermined amount of time based on the monitoring interval specified through the Set-VMReplicationServer cmdlet.

## EXAMPLES

### Example 1
```
PS C:\>Measure-VMReplication
```

This example gets the replication monitoring details of all replicating virtual machines on the local host.

### Example 2
```
PS C:\>Measure-VMReplication VM01
```

This example gets the replication monitoring details of a virtual machine named VM01.

### Example 3
```
PS C:\> Measure-VMReplication -ReplicationHealth Warning
```

This example gets the replication monitoring details of all virtual machines that have a replication health of "Warning".

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which to get replication statistics.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: PrimaryServer

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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine for which you want to get virtual machine replication statistics.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: Name

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ReplicaServerName
Specifies the name of a Replica server of the virtual machines whose replication statistics you want to get.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: Health

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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: Mode

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicationState
Specifies the replication state of the virtual machines for which you want to get replication statistics.
Valid values are:

Error

FailOverWaitingCompletion

FailedOver

NotApplicable

ReadyForInitialReplication

Replicating

Resynchronizing

ResynchronizeSuspended

Suspended

SyncedReplicationComplete

WaitingForInitialReplication

WaitingForStartResynchronize

```yaml
Type: VMReplicationState
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: State

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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### VMReplicationHealth

## NOTES

## RELATED LINKS



