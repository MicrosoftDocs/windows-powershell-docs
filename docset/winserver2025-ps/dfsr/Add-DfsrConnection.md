---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/add-dfsrconnection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DfsrConnection
---

# Add-DfsrConnection

## SYNOPSIS
Creates a connection between members of a replication group.

## SYNTAX

```
Add-DfsrConnection [-GroupName] <String[]> [-SourceComputerName] <String> [-DestinationComputerName] <String>
 [-DisableConnection] [-DisableRDC] [-DisableCrossFileRDC] [[-Description] <String>]
 [[-MinimumRDCFileSizeInKB] <Int64>] [-CreateOneWay] [[-DomainName] <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-DfsrConnection** cmdlet creates a connection between members of a replication group.

Distributed File System (DFS) Replication connections are the logical partnerships between members in a replication group.
The DFS Replication service uses the Remote Procedure Call (RPC) protocol to communicate between servers.
You must create a connection between a pair of computers before the DFS Replication service can initiate replication.
You should always create connections bidirectionally between two servers, even if you are using read-only replication.
The exception to this case is if you create a ring topology between three or more servers, where all members transitively replicate to all partners, and where all servers are hosting only writable replicated folders.

This cmdlet does not support modifying connection bandwidth or schedules, which typically do not require changes.

## EXAMPLES

### Example 1: Create a bidirectional connection between members of a replication group
```
PS C:\> Add-DfsrConnection -GroupName "RG24" -SourceComputerName "SRV01" -DestinationComputerName "SRV02"

GroupName               : RG24
SourceComputerName      : SRV01
DestinationComputerName : SRV02
DomainName              : corp.contoso.com
Identifier              : c33eaaf1-9e50-4510-8484-68271bf93b25c33eaaf1-9e50-4510-8484-68271bf93b25
Enabled                 : True
RdcEnabled              : True
CrossFileRdcEnabled     : True
Description             :
MinimumRDCFileSizeInKB  : 64
State                   : Normal

GroupName               : RG24
SourceComputerName      : SRV02
DestinationComputerName : SRV01
DomainName              : corp.contoso.com
Identifier              : 97c3603a-7828-4403-adac-49575c9e5921
Enabled                 : True
RdcEnabled              : True
CrossFileRdcEnabled     : True
Description             :
MinimumRDCFileSizeInKB  : 64
State                   :

NormalGroupName         : RG24
SourceComputerName      : SRV02
DestinationComputerName : SRV01
DomainName              : corp.contoso.com
Identifier              : 97c3603a-7828-4403-adac-49575c9e5921
Enabled                 : True
RdcEnabled              : True
CrossFileRdcEnabled     : True
Description             :
MinimumRDCFileSizeInKB  : 64
State                   : Normal
```

This command creates a bidirectional replication connection between the computer named SRV01 and the computer named SRV02 in the replication group named RG24.

### Example 2: Create a one-way connection between members of a replication group
```
PS C:\> Add-DfsrConnection -GroupName "RG24" -SourceComputerName SRV02 -DestinationComputerName "SRV01" -CreateOneWay

GroupName               : rg24
SendingComputerName     : SRV02
ReceivingComputerName   : SRV01
DomainName              : corp.contoso.com
Identifier              : c33eaaf1-9e50-4510-8484-68271bf93b25
Enabled                 : True
RdcEnabled              : true
CrossFileRdcEnabled     : True
Description             :
MinimumRDCFileSizeInKB  : 64
State                   : Normal
```

This command creates a one-way replication connection from computer named SRV02 to the computer named SRV01 in the replication group named RG24.
To create a one-way replication connection, you must run the cmdlet once in each direction between members of the replication group.
DFS Replication supports one-way connections only for a ring topology configuration on three or more servers.

### Example 3: Create a data distribution replication topology
```
The first command uses the **New-DfsReplicationGroup** cmdlet to create a replication group object named Branch Office 1, and passes the object to the **New-DfsReplicatedFolder** cmdlet by using the pipe operator. The **New-DfsReplicatedFolder** cmdlet creates a replication folder object named Data Distribution 1, and passes the object to the **Add-DfsrMember** cmdlet by using the pipe operator. The **Add-DfsrMember** cmdlet adds the computers named SRV01, SRV02, and SRV03 to the replication group named Branch Office 1.
PS C:\> New-DfsReplicationGroup -GroupName "Branch Office 1" | New-DfsReplicatedFolder -FolderName "Data Distribution 1" | Add-DfsrMember -ComputerName "SRV01","SRV02","SRV03" | Format-Table dnsname,groupname -auto -wrap
DnsName                 GroupName
-------               ---------
SRV01.corp.contoso.com Branch Office 1
SRV02.corp.contoso.com Branch Office 1
SRV03.corp.contoso.com Branch Office 1

The second command creates a bidirectional replication connection between the computer named SRV01 and the computer named SRV02 in the replication group named Branch Office 1.
PS C:\> Add-DfsrConnection -GroupName "Branch Office 1" -SourceComputerName SRV01 -DestinationComputerName SRV02 | Format-Table *name -wrap -auto
GroupName       SourceComputerName DestinationComputerName
---------       ------------------ -----------------------
Branch Office 1 SRV01               SRV02
Branch Office 1 SRV02               SRV01

The third command creates a bidirectional replication connection between the computer named SRV01 and the computer named SRV03 in the replication group named Branch Office 1.
PS C:\> Add-DfsrConnection -GroupName "Branch Office 1" -SourceComputerName SRV01 -DestinationComputerName SRV03 | Format-Table *name -wrap -auto
GroupName       SourceComputerName DestinationComputerName
---------       ------------------ -----------------------
Branch Office 1 SRV01               SRV03
Branch Office 1 SRV03               SRV01

The fourth command uses the **Set-DfsrMembership** cmdlet to configure membership settings for the primary member of the replication group named Branch Office 1. The command specifies that the computer named SRV01 is the primary member of the group. The command sets an appropriate quota size of the staging folder instead of the lower default.
PS C:\> Set-DfsrMembership -GroupName "Branch Office 1" -FolderName "Data Distribution 1" -ContentPath c:\rf1 -ComputerName SRV01 -PrimaryMember $True -StagingPathQuotaInMB 16384 -Force | Format-Table *name,*path,primary* -auto -wrap
DomainName       GroupName       FolderName          ComputerName ContentPath StagingPath                PrimaryMember
----------       ---------       ----------          ------------ ----------- -----------                -------------
corp.contoso.com Branch Office 1 Data Distribution 1 SRV01         c:\rf1      c:\rf1\DfsrPrivate\Staging          True

The last command uses the **Set-DfsrMembership** cmdlet to configure membership settings for the members of the replication group named Branch Office 1. The command specifies that the computers named SRV02 and SRV03 are members of the group. The command sets an appropriate quota size of the staging folder instead of the lower default.
PS C:\> Set-DfsrMembership -GroupName "Branch Office 1" -FolderName "Data Distribution 1" -ContentPath c:\rf1 -ComputerName SRV02,SRV03 -StagingPathQuotaInMB 16384 -Force | Format-Table *name,*path,primary* -auto -wrap
DomainName       GroupName       FolderName          ComputerName ContentPath StagingPath                PrimaryMember
----------       ---------       ----------          ------------ ----------- -----------                -------------
corp.contoso.com Branch Office 1 Data Distribution 1 SRV02         c:\rf1      c:\rf1\DfsrPrivate\Staging         False
corp.contoso.com Branch Office 1 Data Distribution 1 SRV03         c:\rf1      c:\rf1\DfsrPrivate\Staging         False
```

This example creates a hub and spoke data distribution replication topology.

## PARAMETERS

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

### -CreateOneWay
Specifies that the DFSR service does not create a matching connection in the opposite direction between the two computers.

You do not typically need to specify this parameter.
DFS Replication requires a fully-connected replication topology, which means that all servers have both an inbound and outbound connection between each of its direct partners, or through transitive replication.
This is required even when you specify read-only replication by using the **Set-DfsrMembership** cmdlet and setting the *ReadOnly* parameter to $True.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the connection.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationComputerName
Specifies the name of the receiving computer.
A receiving computer is also called an inbound or downstream computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ReceivingMember, RMem

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisableConnection
Specifies that the DFSR service disables the connection.

You do not typically need to disable a connection.
Specify this parameter to temporarily pause replication.
You can also use the **Suspend-DfsReplicationGroup** cmdlet to halt replication between computers.
You must enable a connection between the computers before the DFS Replication service can initiate replication.

Important: Specify this parameter instead of disabling a computer's membership in the replication group by using the **Set-DfsrMembership** cmdlet.
Disabling and enabling a computer's membership will cause non-authoritative inbound replication.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableCrossFileRDC
Indicates that the DFSR service disables the cross-file similarity Remote Differential Compression (RDC) algorithm on this connection.

Cross-file RDC uses up to five existing previously replicated files on a volume to seed a new replicating file.
Applying cross-file RDC over very low-bandwidth network connections with files that are very similar results in very large bandwidth savings and potentially large time savings.
When you use cross-file RDC on very high-bandwidth network connections, cross-file RDC may add too much local processing time and negatively affect performance.
In extremely large datasets (millions of files on a volume with a great deal of similarity), cross-file RDC may also negatively affect CPU and disk utilization.
Consider disabling cross-file RDC during initial synchronization when you replicate over LANs and very high performance WANs.
This setting is only supported on Windows Server 2012 R2 and later.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableRDC
Indicates that the DFS Replication service creates the connection with Remote Differential Compression (RDC) disabled.

You do not typically need to specify this parameter when you use lower bandwidth, higher latency connections.
Consider specifying this parameter if the connection is over a LAN or very high performance WAN connection.
By default, RDC is enabled on DFS Replication connections.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName
Specifies the NetBIOS name or fully qualified domain name (FQDN) for the Active Directory Domain Service (AD DS) domain that contains the replication group.
If you do not specify this parameter, the cmdlet uses the domain of the current user.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 100
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GroupName
Specifies an array of names of replication groups.
You can use a comma separated list and the wildcard character (*).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: RG, RgName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -MinimumRDCFileSizeInKB
Specifies the file size threshold, in kilobytes, for RDC to apply.

You do not typically need to specify this parameter when you use lower bandwidth/higher latency connections.
Consider specifying this parameter only if the connection is over a LAN or a very high performance WAN connection.
By default, any files equal to or greater than 64KB are chunked by RDC.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceComputerName
Specifies the name of the sending computer.
A sending computer is also called an outbound or upstream computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SendingMember, SMem

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsrConnection

## NOTES

## RELATED LINKS

[Get-DfsrConnection](./Get-DfsrConnection.md)

[Set-DfsrConnection](./Set-DfsrConnection.md)

[Remove-DfsrConnection](./Remove-DfsrConnection.md)

