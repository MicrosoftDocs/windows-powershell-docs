---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmreplication?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMReplication

## SYNOPSIS
Gets the replication settings for a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMReplication [[-VMName] <String[]>] [-ComputerName <String[]>] [-PrimaryServerName <String>]
 [-ReplicaServerName <String>] [-ReplicationHealth <VMReplicationHealthState>]
 [-ReplicationMode <VMReplicationMode>] [-ReplicationState <VMReplicationState>] [-TrustGroup <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMReplication [-VM] <VirtualMachine[]>
```

## DESCRIPTION
The **Get-VMReplication** cmdlet gets the replication settings for a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMReplication
```

This example gets the replication settings of all replication-enabled virtual machines on the local Hyper-V host.

### Example 2
```
PS C:\>Get-VMReplication VM01
```

This example gets the replication settings of a virtual machine named VM01.

### Example 3
```
PS C:\>Get-VMReplication -ReplicaServerName server01.domain01.contoso.com
```

This example gets the replication settings of all virtual machines replicating to server server01.domain01.contoso.com.

### Example 4
```
PS C:\>Get-VMReplication -ReplicationState Replicating
```

This example gets the replication settings of all virtual machines in the Replicating state.

### Example 5
```
PS C:\>Get-VMReplication -TrustGroup DEFAULT
```

This example gets the replication settings of all virtual machines in a trust group named DEFAULT.

### Example 6
```
PS C:\>Get-VMReplication -ReplicationMode Primary
```

This example gets the replication settings of all primary virtual machines on the local host.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which virtual machine replication settings are to be retrieved.
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
Specifies the primary server of the virtual machines whose replication settings are to be retrieved.

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
Specifies the virtual machine whose replication settings are to be retrieved.

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
Specifies the name of the virtual machine whose replication settings are to be retrieved.

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
Specifies the replica server name of the virtual machines whose replication settings are to be retrieved.

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
Gets replication settings for virtual machines with the specified replication health state.
Valid values are Normal, Warning, and Critical.

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
Gets the replication settings for virtual machines with the specified replication mode.
Valid values are None, Primary, Replica, and TestReplica.

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
Gets replication settings for virtual machines with the specified replication state.
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
Specifies the trust group of the virtual machines whose replication settings you want to retrieve.

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

### VMReplication

## NOTES

## RELATED LINKS



