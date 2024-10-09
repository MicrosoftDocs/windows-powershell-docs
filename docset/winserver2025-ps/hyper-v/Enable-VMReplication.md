---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/enable-vmreplication?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-VMReplication
---

# Enable-VMReplication

## SYNOPSIS
Enables replication of a virtual machine.

## SYNTAX

### VMName (Default)
```
Enable-VMReplication [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String[]> [-ReplicaServerName] <String> [-ReplicaServerPort] <Int32>
 [-AuthenticationType] <ReplicationAuthenticationType> [-CertificateThumbprint <String>]
 [-CompressionEnabled <Boolean>] [-ReplicateHostKvpItems <Boolean>] [-BypassProxyServer <Boolean>]
 [-EnableWriteOrderPreservationAcrossDisks <Boolean>] [-VSSSnapshotFrequencyHour <Int32>]
 [-RecoveryHistory <Int32>] [-ReplicationFrequencySec <Int32>] [-ExcludedVhd <HardDiskDrive[]>]
 [-ExcludedVhdPath <String[]>] [-AutoResynchronizeEnabled <Boolean>]
 [-AutoResynchronizeIntervalStart <TimeSpan>] [-AutoResynchronizeIntervalEnd <TimeSpan>] [-AsJob] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMName_AsReplica
```
Enable-VMReplication [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String[]> [-AsReplica] [-AllowedPrimaryServer <String>] [-AsJob] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMObject
```
Enable-VMReplication [-Credential <PSCredential[]>] [-VM] <VirtualMachine[]> [-ReplicaServerName] <String>
 [-ReplicaServerPort] <Int32> [-AuthenticationType] <ReplicationAuthenticationType>
 [-CertificateThumbprint <String>] [-CompressionEnabled <Boolean>] [-ReplicateHostKvpItems <Boolean>]
 [-BypassProxyServer <Boolean>] [-EnableWriteOrderPreservationAcrossDisks <Boolean>]
 [-VSSSnapshotFrequencyHour <Int32>] [-RecoveryHistory <Int32>] [-ReplicationFrequencySec <Int32>]
 [-ExcludedVhd <HardDiskDrive[]>] [-ExcludedVhdPath <String[]>] [-AutoResynchronizeEnabled <Boolean>]
 [-AutoResynchronizeIntervalStart <TimeSpan>] [-AutoResynchronizeIntervalEnd <TimeSpan>] [-AsJob] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject_AsReplica
```
Enable-VMReplication [-Credential <PSCredential[]>] [-VM] <VirtualMachine[]> [-AsReplica]
 [-AllowedPrimaryServer <String>] [-AsJob] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-VMReplication** cmdlet enables replication of a virtual machine to a specified Replica server.

## EXAMPLES

### Example 1
```
PS C:\>  Enable-VMReplication VM01 server01.domain01.contoso.com 80 Kerberos
```

This example configures replication for a virtual machine named VM01 on the local Hyper-V host and directs replication traffic to port 80 on a Replica server named server01.domain01.contoso.com, using Kerberos as the type of authentication.

### Example 2
```
PS C:\>  Enable-VMReplication * server01.domain01.contoso.com 80 Kerberos
```

This example configures replication for all virtual machines on the local Hyper-V host to replica server and directs replication traffic to port 80 on a Replica server named server01.domain01.contoso.com, using Kerberos as the type of authentication.

### Example 3
```
PS C:\>  Enable-VMReplication VM01 -AsReplica -AllowedPrimaryServer *.domain01.contoso.com
```

This example configures a virtual machine VM02 as a replica virtual machine and allows replication of the primary virtual machine from all primary servers that belong to a domain named domain01.contoso.com.

## PARAMETERS

### -AllowedPrimaryServer
When you use the AsReplica parameter to specify a virtual machine as a replica virtual machine, this parameter determines which primary servers can send replication to the replica virtual machine.
Replication is accepted only from the server specified in the chosen authentication entry, or any other authentication entry that has the same trust group.

```yaml
Type: String
Parameter Sets: VMName_AsReplica, VMObject_AsReplica
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
Parameter Sets: VMName_AsReplica, VMObject_AsReplica
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
Parameter Sets: VMName, VMObject
Aliases: AuthType
Accepted values: Kerberos, Certificate

Required: True
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
Parameter Sets: VMName, VMObject
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
Parameter Sets: VMName, VMObject
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
Parameter Sets: VMName, VMObject
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
Parameter Sets: VMName, VMObject
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

The requirement for the subject common name (CN) differs depending on whether the virtual machine belongs to a cluster. For virtual machines that do not belong to a cluster, the subject common name (CN) must be equal to, or subject alternative name (DNS Name) should contain, the FQDN of the host. For virtual machines that belong to a cluster, the subject common name (CN) must be equal to, or subject alternative name (DNS Name) must contain, the and fully qualified domain name (FQDN) of the Hyper-V Replica Broker.

To display a list of certificates in the computer's My store and the thumbprint of each certificate, type the following:

`PS C:\\\> cd cert:\LocalMachine\My`

`PS C:\\\> dir | format-list`

For more information about certificate stores, see [http://technet.microsoft.com//library/cc757138.aspx](https://technet.microsoft.com//library/cc757138.aspx).

```yaml
Type: String
Parameter Sets: VMName, VMObject
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
Parameter Sets: VMName, VMName_AsReplica
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompressionEnabled
Specifies whether to compress replication data for this virtual machine when it is sent over the network.

```yaml
Type: Boolean
Parameter Sets: VMName, VMObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts that have the virtual machines for which you want to enable replication.
NetBIOS names, IP addresses, and fully qualified domain names (FQDN) are allowed.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName, VMName_AsReplica
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

### -EnableWriteOrderPreservationAcrossDisks
Determines whether all virtual hard disks selected for replication are replicated to the same point in time.
This is useful if the virtual machine runs an application that saves data across virtual hard disks (for example, one virtual hard disk dedicated for application data, and another virtual hard disk dedicated for application log files).

```yaml
Type: Boolean
Parameter Sets: VMName, VMObject
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
Parameter Sets: VMName, VMObject
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
Parameter Sets: VMName, VMObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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
You can configure as many as 24 recovery points to be stored.

```yaml
Type: Int32
Parameter Sets: VMName, VMObject
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
Parameter Sets: VMName, VMObject
Aliases: ReplicaServer

Required: True
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
Parameter Sets: VMName, VMObject
Aliases: ReplicaPort

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicateHostKvpItems
Specifies whether to replicate host-only key value pairs (KVP) for this virtual machine.

```yaml
Type: Boolean
Parameter Sets: VMName, VMObject
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
Parameter Sets: VMName, VMObject
Aliases: RepFreq

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
Parameter Sets: VMObject, VMObject_AsReplica
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine you want to configure for replication.

```yaml
Type: String[]
Parameter Sets: VMName, VMName_AsReplica
Aliases: Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VSSSnapshotFrequencyHour
Specifies the frequency, in hours, at which Volume Shadow Copy Service (VSS) performs a snapshot backup of the virtual machines.
Specify this parameter only if application-consistent replication is enabled for the virtual machines and the value you set for the **RecoveryHistory** parameter is not zero.
The cmdlet sets a value of zero for this parameter if application-consistent replication is disabled.
Do not specify this parameter if you are extending replication from the Replica virtual machine.

```yaml
Type: Int32
Parameter Sets: VMName, VMObject
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

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

