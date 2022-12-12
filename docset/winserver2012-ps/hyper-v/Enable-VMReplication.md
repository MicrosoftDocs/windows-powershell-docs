---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/enable-vmreplication?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Enable-VMReplication

## SYNOPSIS
Enables replication of a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Enable-VMReplication [-VMName] <String[]> [-ReplicaServerName] <String> [-ReplicaServerPort] <Int32>
 [-AuthenticationType] <ReplicationAuthenticationType> [-AsJob] [-AutoResynchronizeEnabled <Boolean>]
 [-AutoResynchronizeIntervalEnd <TimeSpan>] [-AutoResynchronizeIntervalStart <TimeSpan>]
 [-BypassProxyServer <Boolean>] [-CertificateThumbprint <String>] [-CompressionEnabled <Boolean>]
 [-ComputerName <String[]>] [-EnableWriteOrderPreservationAcrossDisks <Boolean>]
 [-ExcludedVhd <HardDiskDrive[]>] [-ExcludedVhdPath <String[]>] [-PassThru] [-RecoveryHistory <Int32>]
 [-ReplicateHostKvpItems <Boolean>] [-VSSSnapshotFrequency <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Enable-VMReplication [-VM] <VirtualMachine[]> [-AllowedPrimaryServer <String>] [-AsJob] [-AsReplica]
 [-PassThru] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Enable-VMReplication [-VMName] <String[]> [-AllowedPrimaryServer <String>] [-AsJob] [-AsReplica]
 [-ComputerName <String[]>] [-PassThru] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Enable-VMReplication [-VM] <VirtualMachine[]> [-ReplicaServerName] <String> [-ReplicaServerPort] <Int32>
 [-AuthenticationType] <ReplicationAuthenticationType> [-AsJob] [-AutoResynchronizeEnabled <Boolean>]
 [-AutoResynchronizeIntervalEnd <TimeSpan>] [-AutoResynchronizeIntervalStart <TimeSpan>]
 [-BypassProxyServer <Boolean>] [-CertificateThumbprint <String>] [-CompressionEnabled <Boolean>]
 [-EnableWriteOrderPreservationAcrossDisks <Boolean>] [-ExcludedVhd <HardDiskDrive[]>]
 [-ExcludedVhdPath <String[]>] [-PassThru] [-RecoveryHistory <Int32>] [-ReplicateHostKvpItems <Boolean>]
 [-VSSSnapshotFrequency <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Enable-VMReplication** cmdlet enables replication of a virtual machine to a specified Replica server.

## EXAMPLES

### Example 1
```
PS C:\> Enable-VMReplication VM01 server01.domain01.contoso.com 80 Kerberos
```

This example configures replication for a virtual machine named VM01 on the local Hyper-V host and directs replication traffic to port 80 on a Replica server named server01.domain01.contoso.com, using Kerberos as the type of authentication.

### Example 2
```
PS C:\> Enable-VMReplication * server01.domain01.contoso.com 80 Kerberos
```

This example configures replication for all virtual machines on the local Hyper-V host to replica server and directs replication traffic to port 80 on a Replica server named server01.domain01.contoso.com, using Kerberos as the type of authentication.

### Example 3
```
PS C:\> Enable-VMReplication VM01 -AsReplica -AllowedPrimaryServer *.domain01.contoso.com
```

This example configures a virtual machine VM02 as a replica virtual machine and allows replication of the primary virtual machine from all primary servers that belong to a domain named domain01.contoso.com.

## PARAMETERS

### -AllowedPrimaryServer
When you use the AsReplica parameter to specify a virtual machine as a replica virtual machine, this parameter determines which primary servers can send replication to the replica virtual machine.
Replication is accepted only from the server specified in the chosen authentication entry, or any other authentication entry that has the same trust group.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: AllowedPS

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -AsReplica
Specifies that the virtual machine is a replica virtual machine, enabling it to be used as the source for the initial replication of the primary virtual machine.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: AuthType

Required: True
Position: 4
Default value: None
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: AutoResync

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutoResynchronizeIntervalEnd
Specifies the end of the time period in which you want resynchronization to start automatically.

```yaml
Type: TimeSpan
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: AutoResyncEnd

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutoResynchronizeIntervalStart
Specifies the start of the time period in which you want resynchronization to start automatically.

```yaml
Type: TimeSpan
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: AutoResyncStart

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BypassProxyServer
Specifies whether to bypass a proxy server while replicating data to the Replica server.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: Thumbprint,Cert

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CompressionEnabled
Specifies whether to compress replication data for this virtual machine when it is sent over the network.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts that have the virtual machines for which you want to enable replication.
NetBIOS names, IP addresses, and fully-qualified domain names (FQDN) are allowed.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableWriteOrderPreservationAcrossDisks
Determines whether all virtual hard disks selected for replication are replicated to the same point in time.
This is useful if the virtual machine runs an application that saves data across virtual hard disks (for example, one virtual hard disk dedicated for application data, and another virtual hard disk dedicated for application log files).

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludedVhd
Specifies one or more virtual hard disks to exclude from replication (for example, a virtual hard disk dedicated for the paging file).
Be careful not to exclude virtual hard disks that are critical to the virtual machine's ability to start up, such as the virtual hard disk that stores the guest operating system.
Excluding a critical disk could prevent the replica virtual machine from starting up properly.

```yaml
Type: HardDiskDrive[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludedVhdPath
Specifies the fully qualified path names to the virtual hard disks to exclude from replication.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Specifies that a **VMReplication** object is to be passed through to the pipeline representing the replication.

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
Specifies whether to store additional recovery points on the replica virtual machine.
Storing more than the most recent recovery point of the primary virtual machine allows you to recover to an earlier point in time.
However, storing additional recovery points requires more storage and processing resources.
You can configure as many as 15 recovery points to be stored.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: RecHist

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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: ReplicaServer

Required: True
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: ReplicaPort

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicateHostKvpItems
Specifies whether to replicate host-only key value pairs (KVP) for this virtual machine.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine you want to configure for replication.

```yaml
Type: VirtualMachine[]
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine you want to configure for replication.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: VSSFreq

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

### 
None.

## OUTPUTS

### 
None.

## NOTES

## RELATED LINKS

