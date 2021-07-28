---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WvrAdminTasks.cdxml-help.xml
Module Name: StorageReplica
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/storagereplica/set-srnetworkconstraint?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-SRNetworkConstraint
---

# Set-SRNetworkConstraint

## SYNOPSIS
Creates or modifies a replication network constraint for servers and partnerships.

## SYNTAX

```
Set-SRNetworkConstraint [[-SourceComputerName] <String>] [[-SourceRGName] <String>]
 [-SourceNWInterface] <String[]> [[-DestinationComputerName] <String>] [[-DestinationRGName] <String>]
 [-DestinationNWInterface] <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SRNetworkConstraint** cmdlet creates or modifies a replication network constraint for servers and partnerships.
You can apply network constraints to one or more network adapter interfaces, in order to control which networks Storage Replica can use.
Any networks not specified by this cmdlet are no longer used by Storage Replica.

## EXAMPLES

### Example 1: Set a constraint for stand-alone computers

This command lists available interface indexes by using the **Get-NetIPConfiguration** cmdlet. Run this command on both servers.

```
PS C:\>Get-NetIPConfiguration
InterfaceAlias       : Ethernet
InterfaceIndex       : 2
InterfaceDescription : Microsoft Hyper-V Network Adapter
NetProfile.Name      : Threshold.nttest.microsoft.com
IPv6Address          : 2001:4898:f0:10d1:4037:4c52:6fa4:fe7f
IPv4Address          : 172.24.19.182
IPv6DefaultGateway   : fe80::ea65:49ff:fecd:4141
IPv4DefaultGateway   : 172.24.18.1
DNSServer            : 10.177.9.210
                       10.177.9.211

InterfaceAlias       : Ethernet 2
InterfaceIndex       : 3
InterfaceDescription : Microsoft Hyper-V Network Adapter #2
NetProfile.Name      : Threshold.nttest.microsoft.com
IPv6Address          : 2001:4898:f0:10d1:20d9:301e:9af9:8b4e
IPv4Address          : 172.24.18.180
IPv6DefaultGateway   : fe80::ea65:49ff:fecd:4141
IPv4DefaultGateway   : 172.24.18.1
DNSServer            : 10.177.9.210
                       10.177.9.211
```

The next command sets the network constraint for interfaces and replication groups. The final command makes sure that the constraint takes effect immediately by using the Update-SmbMultichannelConnection cmdlet.

```
PS C:\>Set-SRNetworkConstraint -SourceComputerName "SR-SRV06" -SourceRGName "ReplicationGroup02" -SourceNWInterface 6 -DestinationComputerName "SR-SRV05" -DestinationRGName "ReplicationGroup01" -DestinationNWInterface 2
C:\PS> Update-SmbMultichannelConnection
```

This example sets the network constraint for interfaces and replication groups on stand-alone computers.

### Example 2: Set a constraint for a stretch cluster
```
PS C:\>Set-SRNetworkConstraint -SourceComputerName "SR-SRV01" -SourceRGName "Group01" -SourceNWInterface "Cluster Network 1","Cluster Network 2" -DestinationComputerName "SR-SRV03" -DestinationRGName "Group02" -DestinationNWInterface "Cluster Network 1","Cluster Network 2"
```

This command sets a network constraint for a specific set of cluster networks in a stretch cluster.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationComputerName
Specifies a single replica host computer NetBIOS name or fully qualified domain name (FQDN) of the destination computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DCN

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationNWInterface
Specifies an array of network interfaces.
Specify the interfaces for Storage Replica to use.
Other interfaces no longer accept Storage Replica traffic.

You can display these interfaces by using the Get-NetIPConfiguration cmdlet for stand-alone servers and the Get-ClusterNetwork cmdlet on failover clusters.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: DNI

Required: True
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationRGName
Specifies the name of the destination replication group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DGN

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceComputerName
Specifies a single replica host computer NetBIOS name or FQDN of the source computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SCN

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceNWInterface
Specifies an array of network interfaces.
Specify the interfaces for Storage Replica to use.
Other interfaces no longer accept Storage Replica traffic.

You can display these interfaces by using **Get-NetIPConfiguration** and **Get-ClusterNetwork**.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: SNI

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceRGName
Specifies the name of the source replication group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SGN

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell&reg; calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SRNetworkConstraint](./Get-SRNetworkConstraint.md)

[Remove-SRNetworkConstraint](./Remove-SRNetworkConstraint.md)

