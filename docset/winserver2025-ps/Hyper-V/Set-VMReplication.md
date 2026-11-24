---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmreplication?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMReplication
---

# Set-VMReplication

## SYNOPSIS
Modifies the replication settings of a virtual machine.

## SYNTAX

### VMName (Default)
```
Set-VMReplication [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String[]> [[-ReplicaServerName] <String>] [[-ReplicaServerPort] <Int32>]
 [[-AuthenticationType] <ReplicationAuthenticationType>] [-CertificateThumbprint <String>]
 [-CompressionEnabled <Boolean>] [-ReplicateHostKvpItems <Boolean>] [-BypassProxyServer <Boolean>]
 [-EnableWriteOrderPreservationAcrossDisks <Boolean>] [-InitialReplicationStartTime <DateTime>]
 [-DisableVSSSnapshotReplication] [-VSSSnapshotFrequencyHour <Int32>] [-RecoveryHistory <Int32>]
 [-ReplicationFrequencySec <Int32>] [-ReplicatedDisks <HardDiskDrive[]>] [-ReplicatedDiskPaths <String[]>]
 [-Reverse] [-AutoResynchronizeEnabled <Boolean>] [-AutoResynchronizeIntervalStart <TimeSpan>]
 [-AutoResynchronizeIntervalEnd <TimeSpan>] [-AsReplica] [-UseBackup] [-AllowedPrimaryServer <String>] [-AsJob]
 [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Set-VMReplication [-Credential <PSCredential[]>] [-VM] <VirtualMachine[]> [[-ReplicaServerName] <String>]
 [[-ReplicaServerPort] <Int32>] [[-AuthenticationType] <ReplicationAuthenticationType>]
 [-CertificateThumbprint <String>] [-CompressionEnabled <Boolean>] [-ReplicateHostKvpItems <Boolean>]
 [-BypassProxyServer <Boolean>] [-EnableWriteOrderPreservationAcrossDisks <Boolean>]
 [-InitialReplicationStartTime <DateTime>] [-DisableVSSSnapshotReplication] [-VSSSnapshotFrequencyHour <Int32>]
 [-RecoveryHistory <Int32>] [-ReplicationFrequencySec <Int32>] [-ReplicatedDisks <HardDiskDrive[]>]
 [-ReplicatedDiskPaths <String[]>] [-Reverse] [-AutoResynchronizeEnabled <Boolean>]
 [-AutoResynchronizeIntervalStart <TimeSpan>] [-AutoResynchronizeIntervalEnd <TimeSpan>] [-AsReplica]
 [-UseBackup] [-AllowedPrimaryServer <String>] [-AsJob] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMReplication
```
Set-VMReplication [-Credential <PSCredential[]>] [-VMReplication] <VMReplication[]>
 [[-ReplicaServerName] <String>] [[-ReplicaServerPort] <Int32>]
 [[-AuthenticationType] <ReplicationAuthenticationType>] [-CertificateThumbprint <String>]
 [-CompressionEnabled <Boolean>] [-ReplicateHostKvpItems <Boolean>] [-BypassProxyServer <Boolean>]
 [-EnableWriteOrderPreservationAcrossDisks <Boolean>] [-InitialReplicationStartTime <DateTime>]
 [-DisableVSSSnapshotReplication] [-VSSSnapshotFrequencyHour <Int32>] [-RecoveryHistory <Int32>]
 [-ReplicationFrequencySec <Int32>] [-ReplicatedDisks <HardDiskDrive[]>] [-ReplicatedDiskPaths <String[]>]
 [-Reverse] [-AutoResynchronizeEnabled <Boolean>] [-AutoResynchronizeIntervalStart <TimeSpan>]
 [-AutoResynchronizeIntervalEnd <TimeSpan>] [-AsReplica] [-UseBackup] [-AllowedPrimaryServer <String>] [-AsJob]
 [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMReplication** cmdlet modifies the replication settings of a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>  Set-VMReplication VM01 -AutoResynchronizedDisabled $true -AutoResynchronizeIntervalStart "18:30:00" -AutoResynchronizeIntervalEnd "06:00:00"
```

This example configures the auto-resynchronization of virtual machine VM01.

### Example 2
```
PS C:\>  Set-VMReplication VM01 -AsReplica -AllowedPrimaryServer server01.domain01.contoso.com
```

This example configures virtual machine VM01 as a Replica virtual machine, allowing replication from primary server server01 from domain domain01.contoso.com.

### Example 3
```
PS C:\>  Set-VMReplication VM01 -RecoveryHistory 4 -VSSSnapshotFrequency 4
```

This example configures the recovery history and application-consistent recovery points of the virtual machine VM01.

### Example 4
```
PS C:\>  Set-VMReplication VM01 -Reverse
```

This example reverses the replication of virtual machine VM01.

### Example 5
```
PS C:\>  Set-VMReplication * server01.domain01.contoso.com 80
```

This example configures replication for all virtual machines on the local Hyper-V host to Replica server server01.domain01.contoso.com and port 80.

### Example 6
```
PS C:\> $VHDS = @("C:\VHDS\vhd1", "C:\VHDS\vhd2")
PS C:\> Set-VMReplication -VMName "VM01" -ReplicatedDiskPaths $VHDS
```

The first command assigns the paths of the virtual hard disks vhd1 and vhd2 to the **$VHDS** variable.

The second command specifies the two disks in **$VHDS** to be a part of the included disk set for replication of virtual machine VM01.

## PARAMETERS

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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthenticationType
Specifies the authentication type to use for virtual machine replication, either Kerberos or Certificate.
The specified Replica server must support the chosen authentication type.
Run the **Get-VMReplicationServer** cmdlet to verify the authentication configured for the specified Replica server, or contact the administrator of the specified Replica server.

```yaml
Type: ReplicationAuthenticationType
Parameter Sets: (All)
Aliases: AuthType
Accepted values: Kerberos, Certificate

Required: False
Position: 3
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
Parameter Sets: (All)
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
Parameter Sets: (All)
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
Parameter Sets: (All)
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

- It must not be expired.
- It must include both client and server authentication extensions for extended key usage (EKU), and an associated private key.
- It must terminate at a valid root certificate.
- The requirement for the subject common name (CN) differs depending on whether the virtual machine belongs to a cluster. For virtual machines that do not belong to a cluster, the subject common name (CN) must be equal to, or subject alternative name (DNS Name) should contain, the FQDN of the host. For virtual machines that belong to a cluster, the subject common name (CN) must be equal to, or subject alternative name (DNS Name) must contain, the and fully-qualified domain name (FQDN) of the Hyper-V Replica Broker.

To display a list of certificates in the computer's My store and the thumbprint of each certificate, type the following:

`PS C:\\\> cd cert:\LocalMachine\My`

`PS C:\\\> dir | format-list`

For more information about certificate stores, see [http://technet.microsoft.com//library/cc757138.aspx](https://technet.microsoft.com//library/cc757138.aspx).

```yaml
Type: String
Parameter Sets: (All)
Aliases: Thumbprint, Cert

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -CompressionEnabled
Specifies whether replication data sent over the network is to be compressed.

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

### -ComputerName
Specifies one or more Hyper-V hosts on which replication is to be enabled.
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

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
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
Default value: None
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

### -Passthru
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
You can configure as many as 24 recovery points to be stored.

```yaml
Type: Int32
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: ReplicaServer

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicaServerPort
Specifies the port on the Replica server to use for replication traffic.
Make sure you specify a port that is configured on the Replica server to support the same authentication type you specify using the AuthenticationType parameter in this cmdlet.
Run the **Get-VMReplicationServer** cmdlet on the Replica server to check the configuration of the port, or contact the administrator of the specified Replica server.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: ReplicaPort

Required: False
Position: 2
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

### -ReplicatedDiskPaths
Specifies the fully qualified path names of all the virtual hard disks to include for replication.
Be sure to include virtual hard disks that are critical to the ability of the virtual machine to start, such as the guest operating system disk.
Excluding a critical disk from this list could prevent the replica virtual machine from starting properly.

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

### -ReplicatedDisks
Specifies all virtual hard disks to include for replication.
This parameter can include all the VHDs attached to the virtual machine or a subset.
Be sure to include virtual hard disks that are critical to the ability of the virtual machine to start, such as the guest operating system disk.
Excluding a critical disk from this list could prevent the replica virtual machine from starting properly.

```yaml
Type: HardDiskDrive[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicationFrequencySec
Specifies the frequency, in seconds, at which Hyper-V replicates changes to the Replica server.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: RepFreq

Required: False
Position: Named
Default value: None
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

### -VM
Specifies the virtual machine for which the replication configuration is to be set.

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
Specifies the name of the virtual machine for which the replication configuration is to be set.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMReplication
Specifies a virtual machine replication object for which the configuration is to be set.

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

### -VSSSnapshotFrequencyHour
Specifies the frequency, in hours, at which Volume Shadow Copy Service (VSS) performs a snapshot backup of the virtual machines.
Specify this parameter only if application-consistent replication is enabled for the virtual is and the value you set for the **RecoveryHistory** parameter is not zero.
The cmdlet sets a value of zero for this parameter if application-consistent replication is disabled.
Do not specify this parameter if you are extending replication from the Replica virtual machine.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: VSSFreq

Required: False
Position: Named
Default value: None
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### None
Default

### VMReplication
If **-PassThru** is specified.

## NOTES

## RELATED LINKS

