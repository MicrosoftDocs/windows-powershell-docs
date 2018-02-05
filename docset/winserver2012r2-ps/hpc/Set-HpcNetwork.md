---
author:
description:
external help file: CCPPSH.dll-Help.xml
keywords: powershell, cmdlet
manager:
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: http://go.microsoft.com/fwlink/?LinkId=182865
schema: 2.0.0
title: Set-HpcNetwork
ms.assetid: AB7967D6-D254-4421-B957-E6DA6974E2A6
---

# Set-HpcNetwork

## SYNOPSIS
Sets the network topology and the properties of all of the network interfaces for the HPC cluster.

## SYNTAX

```
Set-HpcNetwork [[-Topology] <String>] [-Enterprise <String>] [-EnterpriseFirewall <Boolean>]
 [-EnterpriseDnsRegistrationType <HpcDnsRegistrationType>] [-Private <String>] [-PrivateFirewall <Boolean>]
 [-PrivateDnsRegistrationType <HpcDnsRegistrationType>] [-PrivateDHCP <Boolean>] [-PrivateDHCPClient]
 [-PrivateDHCPDns <String>] [-PrivateDHCPStartAddress <String>] [-PrivateDHCPEndAddress <String>]
 [-PrivateDHCPGateway <String>] [-PrivateNat <Boolean>] [-PrivateIpAddress <String>]
 [-PrivateSubnetMask <String>] [-Application <String>] [-ApplicationFirewall <Boolean>]
 [-ApplicationDnsRegistrationType <HpcDnsRegistrationType>] [-ApplicationDHCP <Boolean>]
 [-ApplicationDHCPClient] [-ApplicationDHCPDns <String>] [-ApplicationDHCPStartAddress <String>]
 [-ApplicationDHCPEndAddress <String>] [-ApplicationDHCPGateway <String>] [-ApplicationNat <Boolean>]
 [-ApplicationIpAddress <String>] [-ApplicationSubnetMask <String>]
 [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HpcNetwork** cmdlet sets the network topology and the properties of all of the network interfaces for the HPC cluster.
Five network topologies are available: Enterprise, Private, EnterprisePrivate, PrivateApplication, EnterprisePrivateApplication.
You can set the properties for three types of network interfaces: Enterprise, Private, and Application.
You can set different properties depending on the type of the network interface.

## EXAMPLES

### Example 1: Set the network topology to Enterprise
```
PS C:\>Set-HpcNetwork -Topology "Enterprise" -Enterprise "NIC_1" -EnterpriseFirewall $True
```

This command sets the network topology for the HPC cluster to Enterprise.
This command also sets a network interface named NIC_1 as the enterprise network interface and turns on the firewall for the Enterprise network on all nodes in the HPC cluster.

### Example 2: Set network interfaces on the head node
```
PS C:\>Set-HpcNetwork -Topology "Private" -Enterprise "NIC_1" -EnterpriseFirewall $True -Private "NIC_2" -PrivateIpAddress "192.168.0.1" -PrivateSubnetMask "255.255.0.0" -PrivateDHCP $True -PrivateDHCPStartAddress "192.168.0.10" -PrivateDHCPEndAddress "192.168.0.200" -PrivateDHCPGateway "192.168.0.1" -PrivateDHCPDns "192.168.0.1" -PrivateNat $True -PrivateFirewall $False
```

This command sets the topology for the HPC cluster to Private.
This example also sets two different network interfaces on the head node to be the Enterprise network interface and the Private network interface.

For the Private network interface, this example sets the subnet and the Dynamic Host Configuration Protocol (DHCP) settings.

### Example 3: Set Enterprise and Private network interfaces
```
PS C:\>Set-HpcNetwork -Topology "EnterprisePrivate" -Enterprise "NIC_1" -EnterpriseFirewall $True -Private "NIC_2" -PrivateIpAddress "192.168.0.1" -PrivateSubnetMask "255.255.0.0" -PrivateDHCP $True -PrivateDHCPStartAddress "192.168.0.10" -PrivateDHCPEndAddress "192.168.0.200" -PrivateDHCPDns "192.168.0.1" -PrivateNat $False -PrivateFirewall $False
```

This command sets the topology for the HPC cluster to EnterprisePrivate.
This example also sets two different network interfaces on the head node to be the Enterprise network interface and the Private network interface.
For the Private network interface, this example sets the subnet and the Dynamic Host Configuration Protocol (DHCP) settings.

### Example 4: Set the network topology to PrivateApplication
```
PS C:\>Set-HpcNetwork -Topology PrivateApplication -Enterprise "NIC_1" -EnterpriseFirewall $True -Private "NIC_2" -PrivateIpAddress "192.168.0.1" -PrivateSubnetMask "255.255.0.0" -PrivateDHCP $True -PrivateDHCPStartAddress "192.168.0.10" -PrivateDHCPEndAddress "192.168.0.200" -PrivateDHCPGateway "192.168.0.1" -PrivateDHCPDns "192.168.0.1" -PrivateNat $True -PrivateFirewall $False -Application "NIC_3" -ApplicationIpAddress "10.0.0.1" -ApplicationSubnetMask "255.255.0.0" -ApplicationDHCP $True -ApplicationDHCPStartAddress "10.0.0.10" -ApplicationDHCPEndAddress "10.0.0.100" -ApplicationDHCPGateway "10.0.0.1" -ApplicationDHCPDns "10.0.0.1" -ApplicationNat $False -ApplicationFirewall $False
```

This command sets the topology for the HPC cluster to PrivateApplication.
This example also sets three different network interfaces on the head node to be the Enterprise network interface, the Private network interface, and the Application network interface.
For the Private and Application network interfaces, this example sets the subnet and the Dynamic Host Configuration Protocol (DHCP) settings.

### Example 5: Set the network topology to EnterprisePrivateApplication
```
PS C:\>Set-HpcNetwork -Topology "EnterprisePrivateApplication" -Enterprise "NIC_1" -EnterpriseFirewall $True -Private "NIC_2" -PrivateIpAddress "192.168.0.1" -PrivateSubnetMask "255.255.0.0" -PrivateDHCP $True -PrivateDHCPStartAddress "192.168.0.10" -PrivateDHCPEndAddress "192.168.0.200" -PrivateDHCPDns "192.168.0.1" -PrivateNat $False -PrivateFirewall $False -Application "NIC_3" -ApplicationIpAddress "10.0.0.1" -ApplicationSubnetMask "255.255.0.0" -ApplicationDHCP $True -ApplicationDHCPStartAddress "10.0.0.10" -ApplicationDHCPEndAddress "10.0.0.100" -ApplicationDHCPDns "10.0.0.1" -ApplicationNat $False -ApplicationFirewall $False
```

This command sets the topology for the HPC cluster to EnterprisePrivateApplication.
This example also sets three different network interfaces on the head node to be the Enterprise network interface, the Private network interface, and the Application network interface.
For the Private and Application network interfaces, this example sets the subnet and the Dynamic Host Configuration Protocol (DHCP) settings.

### Example 6: Register the Private network interface in DNS
```
PS C:\>Set-HpcNetwork -PrivateDnsRegistrationType FullDnsNameOnly
```

This command registers the Private network interface in DNS using the primary DNS suffix appended to the computer name.

## PARAMETERS

### -Application
Specifies the name of the network interface to use for the Application network.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationDHCP
Indicates whether Dynamic Host Configuration Protocol (DHCP) services are turned on for the Application network.
A non-zero or $True value turns on DHCP services, A value of 0 or $False turns off DHCP services.

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

### -ApplicationDHCPClient
Causes the network adapter for the Application network to retrieve its IP address settings from a Dynamic Host Configuration Protocol (DHCP) server on the Application network.

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

### -ApplicationDHCPDns
Specifies the IP address of the Domain Name System (DNS) server that Dynamic Host Configuration Protocol (DHCP) uses on the Application network.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationDHCPEndAddress
Specifies the ending IP address for the Dynamic Host Configuration Protocol (DHCP) scope for the Application network.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationDHCPGateway
Specifies the IP address of the Dynamic Host Configuration Protocol (DHCP) gateway for the Application network.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationDHCPStartAddress
Specifies the starting IP address for the Dynamic Host Configuration Protocol (DHCP) scope for the Application network.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationDnsRegistrationType
Specifies the Domain Name System (DNS) registration type for the Application network.

```yaml
Type: HpcDnsRegistrationType
Parameter Sets: (All)
Aliases:
Accepted values: FullDnsNameOnly, None, WithConnectionDnsSuffix

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationFirewall
Indicates whether to turn on the firewall for the Application network on all nodes in the HPC cluster.
A non-zero or $True value turns on the firewall for the Application network on all nodes in the HPC cluster.
A value of 0 or $False turns off the firewall for the Application network on all nodes in the cluster.
A $Null value maintains the current firewall settings for the Application network across the HPC cluster.

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

### -ApplicationIpAddress
Specifies the IP address of the network interface for the head node on the Application network.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationNat
Indicates whether to turn on network address translation (NAT) on the Application network.
A non-zero or $True value turns on NAT.
A value of 0 or $False turns off NAT.

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

### -ApplicationSubnetMask
Specifies the subnet mask to use for the Application network.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enterprise
Specifies the name of the network interface to use for the Enterprise network.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnterpriseDnsRegistrationType
Specifies the Domain Name System (DNS) registration type for the Enterprise network.

```yaml
Type: HpcDnsRegistrationType
Parameter Sets: (All)
Aliases:
Accepted values: FullDnsNameOnly, None, WithConnectionDnsSuffix

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnterpriseFirewall
Indicates whether to turn on the firewall for the Enterprise network on all nodes in the HPC cluster.
A non-zero or $True value turns on the firewall for the Enterprise network on all nodes in the HPC cluster.
A value of 0 or $False turns off the firewall for the Enterprise network on all nodes in the cluster.
A $null value maintains the current firewall settings for the Enterprise across the HPC cluster.

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

### -Private
Specifies the name of the network interface to user for the Private network.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateDHCP
Indicates whether Dynamic Host Configuration Protocol (DHCP) services are turned on for the Private network.
A non-zero or $True value turns on DHCP services, A value of 0 or $False turns off DHCP services.

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

### -PrivateDHCPClient
Causes the network adapter for the Private network to retrieve its IP address settings from a Dynamic Host Configuration Protocol (DHCP) server on the Private network.

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

### -PrivateDHCPDns
Specifies the IP address of the Domain Name System (DNS) server that Dynamic Host Configuration Protocol (DHCP) uses on the Private network.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateDHCPEndAddress
Specifies the ending IP address for the Dynamic Host Configuration Protocol (DHCP) scope for the Private network.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateDHCPGateway
Specifies the IP address of the Dynamic Host Configuration Protocol (DHCP) gateway for the Private network.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateDHCPStartAddress
Specifies the starting IP address for the Dynamic Host Configuration Protocol (DHCP) scope for the Private network.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateDnsRegistrationType
Specifies the Domain Name System (DNS) registration type for the Private network.
Valid values are:

- FullDnsNameOnly
- None
- WithConnectionDnsSuffix

```yaml
Type: HpcDnsRegistrationType
Parameter Sets: (All)
Aliases:
Accepted values: FullDnsNameOnly, None, WithConnectionDnsSuffix

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateFirewall
Indicates whether to turn on the firewall for the Private network on all nodes in the HPC cluster.
A non-zero or $True value turns on the firewall for the Private network on all nodes in the HPC cluster.
A value of 0 or $False turns off the firewall for the Private network on all nodes in the cluster.
A $Null value maintains the current firewall settings for the Private network across the HPC cluster.

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

### -PrivateIpAddress
Specifies the IP address of the network interface for the head node on the Private network.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateNat
Indicates whether to turn on NAT on the Private network.
A non-zero or $True value turns on NAT.
A value of 0 or $False turns off NAT.

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

### -PrivateSubnetMask
Specifies the subnet mask to use for the Private network.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster.
The value must be a valid computer name or IP address.
If you do not specify the Scheduler parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.
To set this environment variable, run the following cmdlet:

`Set-Content Env:CCP_SCHEDULER \<head_node_name\>`

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

### -Topology
Specifies the network topology to set for the HPC cluster.
The network topology can be Enterprise, Private, EnterprisePrivate, PrivateApplication, or EnterprisePrivateApplication.
These topologies are defined as follows:

- Enterprise.
All nodes are connected only to an enterprise network.
You only need one network adapter on the head node for this topology.
- Private.
The compute nodes are isolated on a private network.
You need two network adapters on the head node for this topology.
- EnterprisePrivate.
All nodes are connected to both enterprise and private networks.
You need two network adapters on the head node for this topology.
- PrivateApplication.
The compute nodes are isolated on private and application networks.
You need three network adapters on the head node for this topology.
- EnterprisePrivateApplication.
All nodes are connected to enterprise, private, and application networks.
You need three network adapters on the head node for this topology.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


Specifies an array of cluster connection strings for the cluster to which you want to add the device drivers.
The value format is host1,host2,host3.
If you do not specify the *ClusterConnectionString* parameter, this cmdlet uses the connection string on the head node that the CCP_CONNECTIONSTRING environment variable specifies.
To set this environment variable, run the following cmdlet: `Set-Content Env: CCP_CONNECTIONSTRING \<head_node_name\>`.




### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES
* Use the Get-HpcNetworkInterface | Format-List command to get the names of the network interfaces for your HPC cluster.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcNetworkInterface](./Get-HpcNetworkInterface.md)

[Get-HpcNetworkTopology](./Get-HpcNetworkTopology.md)
