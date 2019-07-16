---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Set-VMReplication

## SYNOPSIS
Modifies the replication settings of a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VMReplication [-VMName] <String[]> [[-ReplicaServerName] <String>] [[-ReplicaServerPort] <Int32>]
 [[-AuthenticationType] <ReplicationAuthenticationType>] [-AllowedPrimaryServer <String>] [-AsJob] [-AsReplica]
 [-AutoResynchronizeEnabled <Boolean>] [-AutoResynchronizeIntervalEnd <TimeSpan>]
 [-AutoResynchronizeIntervalStart <TimeSpan>] [-BypassProxyServer <Boolean>] [-CertificateThumbprint <String>]
 [-CompressionEnabled <Boolean>] [-ComputerName <String[]>] [-DisableVSSSnapshotReplication]
 [-EnableWriteOrderPreservationAcrossDisks <Boolean>] [-InitialReplicationStartTime <DateTime>] [-PassThru]
 [-RecoveryHistory <Int32>] [-ReplicateHostKvpItems <Boolean>] [-Reverse] [-UseBackup]
 [-VSSSnapshotFrequency <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-VMReplication [-VM] <VirtualMachine[]> [[-ReplicaServerName] <String>] [[-ReplicaServerPort] <Int32>]
 [[-AuthenticationType] <ReplicationAuthenticationType>] [-AllowedPrimaryServer <String>] [-AsJob] [-AsReplica]
 [-AutoResynchronizeEnabled <Boolean>] [-AutoResynchronizeIntervalEnd <TimeSpan>]
 [-AutoResynchronizeIntervalStart <TimeSpan>] [-BypassProxyServer <Boolean>] [-CertificateThumbprint <String>]
 [-CompressionEnabled <Boolean>] [-DisableVSSSnapshotReplication]
 [-EnableWriteOrderPreservationAcrossDisks <Boolean>] [-InitialReplicationStartTime <DateTime>] [-PassThru]
 [-RecoveryHistory <Int32>] [-ReplicateHostKvpItems <Boolean>] [-Reverse] [-UseBackup]
 [-VSSSnapshotFrequency <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-VMReplication [-VMReplication] <VMReplication[]> [[-ReplicaServerName] <String>]
 [[-ReplicaServerPort] <Int32>] [[-AuthenticationType] <ReplicationAuthenticationType>]
 [-AllowedPrimaryServer <String>] [-AsJob] [-AsReplica] [-AutoResynchronizeEnabled <Boolean>]
 [-AutoResynchronizeIntervalEnd <TimeSpan>] [-AutoResynchronizeIntervalStart <TimeSpan>]
 [-BypassProxyServer <Boolean>] [-CertificateThumbprint <String>] [-CompressionEnabled <Boolean>]
 [-DisableVSSSnapshotReplication] [-EnableWriteOrderPreservationAcrossDisks <Boolean>]
 [-InitialReplicationStartTime <DateTime>] [-PassThru] [-RecoveryHistory <Int32>]
 [-ReplicateHostKvpItems <Boolean>] [-Reverse] [-UseBackup] [-VSSSnapshotFrequency <Int32>] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Set-VMReplication** cmdlet modifies the replication settings of a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Set-VMReplication VM01 -AutoResynchronizedDisabled $true -AutoResynchronizeIntervalStart "18:30:00" -AutoResynchronizeIntervalEnd "06:00:00"
```

This example configures the auto-resynchronization of virtual machine VM01.

### Example 2
```
PS C:\> Set-VMReplication VM01 -AsReplica -AllowedPrimaryServer server01.domain01.contoso.com
```

This example configures virtual machine VM01 as a Replica virtual machine, allowing replication from primary server server01 from domain domain01.contoso.com.

### Example 3
```
PS C:\> Set-VMReplication VM01 -RecoveryHistory 4 -VSSSnapshotFrequency 4
```

This example configures the recovery history and application-consistent recovery points of the virtual machine VM01.

### Example 4
```
PS C:\> Set-VMReplication VM01 -Reverse
```

This example reverses the replication of virtual machine VM01.

### Example 5
```
PS C:\> Set-VMReplication * server01.domain01.contoso.com 80
```

This example configures replication for all virtual machines on the local Hyper-V host to Replica server server01.domain01.contoso.com and port 80.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.

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

### -AuthenticationType
Specifies the authentication type to use for virtual machine replication, either "Kerberos" or "Certificate".
The specified Replica server must support the chosen authentication type.
Run the Get-VMReplicationServer cmdlet to verify the authentication configured for the specified Replica server, or contact the administrator of the specified Replica server.

```yaml
Type: ReplicationAuthenticationType
Parameter Sets: (All)
Aliases: AuthType

Required: False
Position: 4
Default value: Integrated
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutoResynchronizeEnabled
Enables replicating virtual machines that require resynchronization to be resynchronized automatically.
(For example, a virtual machine requires resynchronization if the primary server shuts down abruptly).
Resynchronization requires significant storage and processing resources.
We recommended scheduling resynchronization during off-peak hours to reduce the impact to the host and other virtual machines running on the host.
Use the AutoResynchronizeIntervalStart and AutoResynchronizeIntervalEnd parameters to specify an off-peak time to start the automatic resynchronization.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: AutoResync

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutoResynchronizeIntervalEnd
Specifies the end of the time period in which you want resynchronization to start automatically.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: AutoResyncEnd

Required: False
Position: Named
Default value: 06:00AM
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutoResynchronizeIntervalStart
Specifies the start of the time period in which you want resynchronization to start automatically.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: AutoResyncStart

Required: False
Position: Named
Default value: 06:30PM
Accept pipeline input: False
Accept wildcard characters: False
```

### -BypassProxyServer
Specifies whether to bypass a proxy server while replicating data to the Replica server.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint
Specifies the certificate to use for mutual authentication of the replication data.
This parameter is required only when "Certificate" is specified as the type of authentication.
Specify the thumbprint of a valid computer certificate from the Personal store.

The certificate must have all of the following properties to be valid:

It must not be expired.

It must include both client and server authentication extensions for extended key usage (EKU), and an associated private key.

It must terminate at a valid root certificate.

The requirement for the subject common name (CN) differs depending on whether the virtual machine belongs to a cluster.
For virtual machines that do not belong to a cluster, the subject common name (CN) must be equal to, or subject alternative name (DNS Name) should contain, the FQDN of the host.
For virtual machines that belong to a cluster, the subject common name (CN) must be equal to, or subject alternative name (DNS Name) must contain, the and fully-qualified domain name (FQDN) of the Hyper-V Replica Broker.

To display a list of certificates in the computer's My store and the thumbprint of each certificate, type the following:

`PS C:\\\> cd cert:\LocalMachine\My`

`PS C:\\\> dir | format-list`

For more information about certificate stores, see http://technet.microsoft.com//library/cc757138.aspxhttp://technet.microsoft.com//library/cc757138.aspx.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Thumbprint,Cert

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CompressionEnabled
Specifies whether replication data sent over the network is to be compressed.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which replication is to be enabled.
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

### -InitialReplicationStartTime
Specifies the time to start the initial replication, when scheduling initial replication to occur later.
You can specify a time up to 7 days later.
When this parameter is not specified, initial replication occurs immediately.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: IRTime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Specifies that a **VMReplication** object is to be passed through to the pipeline representing the replication configuration to be set.

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

### -RecoveryHistory
Specifies whether to store additional recovery points on the Replica virtual machine.
Storing more than the most recent recovery point of the primary virtual machine allows you to recover to an earlier point in time.
However, storing additional recovery points requires more storage and processing resources.
You can configure as many as 15 recovery points to be stored.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: RecHist

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Reverse
Reverses the replication of the virtual machine, switching it from a primary virtual machine to a Replica virtual machine, or from a Replica virtual machine to a primary virtual machine.

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

### -VM
Specifies the virtual machine for which the replication configuration is to be set.

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
Specifies the name of the virtual machine for which the replication configuration is to be set.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMReplication
Specifies a virtual machine replication object for which the configuration is to be set.

```yaml
Type: VMReplication[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AsReplica
Specifies that the virtual machine is a replica virtual machine, enabling it to be used as the source for the initial replication of the primary virtual machine.

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

### -DisableVSSSnapshotReplication
Specifies whether to replicate volume shadow copy service (VSS) snapshots.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: DisableVSS

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableWriteOrderPreservationAcrossDisks
Determines whether all virtual hard disks selected for replication are replicated to the same point in time.
This is useful if the virtual machine runs an application that saves data across virtual hard disks (for example, one virtual hard disk dedicated for application data, and another virtual hard disk dedicated for application log files).

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicaServerName
Specifies the name of the Replica server to which this virtual machine will be replicated.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ReplicaServer

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicaServerPort
Specifies the port on the Replica server to use for replication traffic.
Make sure you specify a port that is configured on the Replica server to support the same authentication type you specify using the AuthenticationType parameter in this cmdlet.
Run the Get-VMReplicationServer cmdlet on the Replica server to check the configuration of the port, or contact the administrator of the specified Replica server.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: ReplicaPort

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicateHostKvpItems
Specifies whether to replicate host-only key value pairs (KVP) for this virtual machine.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseBackup
Specifies that a restored copy of the virtual machine on the Replica server is to be used as the source of the initial replication.

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

### -VSSSnapshotFrequency
Specifies how often to replicate volume shadow copy service (VSS) copies of the virtual machine, which are called application-consistent recovery points.
Valid values are in increments of one hour.
You can specify from 1 through 12 hours.
Use of this parameter requires that you also use the "Recovery History" parameter to specify at least one additional recovery point.
Using application-consistent recovery points impacts the performance of applications running in the primary virtual machine when these snapshots are taken.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: VSSFreq

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowedPrimaryServer
When you use the AsReplica parameter to specify a virtual machine as a Replica virtual machine, this parameter determines which primary servers can send replication to the Replica virtual machine.
Replication is accepted only from the server specified in the chosen authentication entry, or any other authentication entry that has the same trust group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AllowedPS

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### None
Default

### VMReplication
If **-PassThru** is specified.

## NOTES

## RELATED LINKS

[00000000-0000-0000-0000-000000000000](00000000-0000-0000-0000-000000000000)

