---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmreplication?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMReplication
---

# Get-VMReplication

## SYNOPSIS
Gets the replication settings for a virtual machine.

## SYNTAX

### VMName (Default)
```
Get-VMReplication [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [[-VMName] <String[]>] [-ReplicaServerName <String>] [-PrimaryServerName <String>]
 [-ReplicationState <VMReplicationState>] [-ReplicationHealth <VMReplicationHealthState>]
 [-ReplicationMode <VMReplicationMode>] [-ReplicationRelationshipType <VMReplicationRelationshipType>]
 [-TrustGroup <String>] [<CommonParameters>]
```

### VMObject
```
Get-VMReplication [-VM] <VirtualMachine[]> [-ReplicationRelationshipType <VMReplicationRelationshipType>]
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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts from which virtual machine replication settings are to be retrieved.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
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
Accepted values: Disabled, ReadyForInitialReplication, InitialReplicationInProgress, WaitingForInitialReplication, Replicating, PreparedForFailover, FailedOverWaitingCompletion, FailedOver, Suspended, Error, WaitingForStartResynchronize, Resynchronizing, ResynchronizeSuspended, RecoveryInProgress, FailbackInProgress, FailbackComplete, WaitingForUpdateCompletion, UpdateError, WaitingForRepurposeCompletion, PreparedForSyncReplication, PreparedForGroupReverseReplication, FiredrillInProgress

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMReplication

## NOTES

## RELATED LINKS

