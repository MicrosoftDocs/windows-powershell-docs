---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmnetworkadapter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMNetworkAdapter
---

# Set-VMNetworkAdapter

## SYNOPSIS
Configures features of the virtual network adapter in a virtual machine or the management operating system.

## SYNTAX

### VMName (Default)
```
Set-VMNetworkAdapter [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String> [-Name <String>] [-DynamicMacAddress] [-StaticMacAddress <String>]
 [-MacAddressSpoofing <OnOffState>] [-DhcpGuard <OnOffState>] [-RouterGuard <OnOffState>]
 [-PortMirroring <VMNetworkAdapterPortMirroringMode>] [-IeeePriorityTag <OnOffState>] [-VmqWeight <UInt32>]
 [-IovQueuePairsRequested <UInt32>] [-IovInterruptModeration <IovInterruptModerationValue>]
 [-IovWeight <UInt32>] [-IPsecOffloadMaximumSecurityAssociation <UInt32>] [-MaximumBandwidth <Int64>]
 [-MinimumBandwidthAbsolute <Int64>] [-MinimumBandwidthWeight <UInt32>] [-MandatoryFeatureId <String[]>]
 [-ResourcePoolName <String>] [-TestReplicaPoolName <String>] [-TestReplicaSwitchName <String>]
 [-VirtualSubnetId <UInt32>] [-AllowTeaming <OnOffState>] [-NotMonitoredInCluster <Boolean>]
 [-StormLimit <UInt32>] [-DynamicIPAddressLimit <UInt32>] [-DeviceNaming <OnOffState>]
 [-FixSpeed10G <OnOffState>] [-PacketDirectNumProcs <UInt32>] [-PacketDirectModerationCount <UInt32>]
 [-PacketDirectModerationInterval <UInt32>] [-VrssEnabled <Boolean>] [-VmmqEnabled <Boolean>]
 [-VmmqQueuePairs <UInt32>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ManagementOS
```
Set-VMNetworkAdapter [-ManagementOS] [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-Name <String>] [-MacAddressSpoofing <OnOffState>] [-DhcpGuard <OnOffState>]
 [-RouterGuard <OnOffState>] [-PortMirroring <VMNetworkAdapterPortMirroringMode>]
 [-IeeePriorityTag <OnOffState>] [-VmqWeight <UInt32>] [-IovQueuePairsRequested <UInt32>]
 [-IovInterruptModeration <IovInterruptModerationValue>] [-IovWeight <UInt32>]
 [-IPsecOffloadMaximumSecurityAssociation <UInt32>] [-MaximumBandwidth <Int64>]
 [-MinimumBandwidthAbsolute <Int64>] [-MinimumBandwidthWeight <UInt32>] [-MandatoryFeatureId <String[]>]
 [-ResourcePoolName <String>] [-TestReplicaPoolName <String>] [-TestReplicaSwitchName <String>]
 [-VirtualSubnetId <UInt32>] [-AllowTeaming <OnOffState>] [-NotMonitoredInCluster <Boolean>]
 [-StormLimit <UInt32>] [-DynamicIPAddressLimit <UInt32>] [-DeviceNaming <OnOffState>]
 [-FixSpeed10G <OnOffState>] [-PacketDirectNumProcs <UInt32>] [-PacketDirectModerationCount <UInt32>]
 [-PacketDirectModerationInterval <UInt32>] [-VrssEnabled <Boolean>] [-VmmqEnabled <Boolean>]
 [-VmmqQueuePairs <UInt32>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceObject
```
Set-VMNetworkAdapter [-VMNetworkAdapter] <VMNetworkAdapterBase> [-DynamicMacAddress]
 [-StaticMacAddress <String>] [-MacAddressSpoofing <OnOffState>] [-DhcpGuard <OnOffState>]
 [-RouterGuard <OnOffState>] [-PortMirroring <VMNetworkAdapterPortMirroringMode>]
 [-IeeePriorityTag <OnOffState>] [-VmqWeight <UInt32>] [-IovQueuePairsRequested <UInt32>]
 [-IovInterruptModeration <IovInterruptModerationValue>] [-IovWeight <UInt32>]
 [-IPsecOffloadMaximumSecurityAssociation <UInt32>] [-MaximumBandwidth <Int64>]
 [-MinimumBandwidthAbsolute <Int64>] [-MinimumBandwidthWeight <UInt32>] [-MandatoryFeatureId <String[]>]
 [-ResourcePoolName <String>] [-TestReplicaPoolName <String>] [-TestReplicaSwitchName <String>]
 [-VirtualSubnetId <UInt32>] [-AllowTeaming <OnOffState>] [-NotMonitoredInCluster <Boolean>]
 [-StormLimit <UInt32>] [-DynamicIPAddressLimit <UInt32>] [-DeviceNaming <OnOffState>]
 [-FixSpeed10G <OnOffState>] [-PacketDirectNumProcs <UInt32>] [-PacketDirectModerationCount <UInt32>]
 [-PacketDirectModerationInterval <UInt32>] [-VrssEnabled <Boolean>] [-VmmqEnabled <Boolean>]
 [-VmmqQueuePairs <UInt32>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Set-VMNetworkAdapter [-VM] <VirtualMachine> [-Name <String>] [-DynamicMacAddress] [-StaticMacAddress <String>]
 [-MacAddressSpoofing <OnOffState>] [-DhcpGuard <OnOffState>] [-RouterGuard <OnOffState>]
 [-PortMirroring <VMNetworkAdapterPortMirroringMode>] [-IeeePriorityTag <OnOffState>] [-VmqWeight <UInt32>]
 [-IovQueuePairsRequested <UInt32>] [-IovInterruptModeration <IovInterruptModerationValue>]
 [-IovWeight <UInt32>] [-IPsecOffloadMaximumSecurityAssociation <UInt32>] [-MaximumBandwidth <Int64>]
 [-MinimumBandwidthAbsolute <Int64>] [-MinimumBandwidthWeight <UInt32>] [-MandatoryFeatureId <String[]>]
 [-ResourcePoolName <String>] [-TestReplicaPoolName <String>] [-TestReplicaSwitchName <String>]
 [-VirtualSubnetId <UInt32>] [-AllowTeaming <OnOffState>] [-NotMonitoredInCluster <Boolean>]
 [-StormLimit <UInt32>] [-DynamicIPAddressLimit <UInt32>] [-DeviceNaming <OnOffState>]
 [-FixSpeed10G <OnOffState>] [-PacketDirectNumProcs <UInt32>] [-PacketDirectModerationCount <UInt32>]
 [-PacketDirectModerationInterval <UInt32>] [-VrssEnabled <Boolean>] [-VmmqEnabled <Boolean>]
 [-VmmqQueuePairs <UInt32>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMNetworkAdapter** cmdlet configures features of the virtual network adapter in a virtual machine or the management operating system.

## EXAMPLES

### Example 1
```
PS C:\> Set-VMNetworkAdapter -VMName Redmond -DhcpGuard On
```

This example enables DHCP Guard on all the virtual network adapters of virtual machine Redmond.
When DHCP Guard enabled, if virtual machine Redmond replies to requests from DHCP clients, these replies are dropped.

### Example 2
```
PS C:\> Set-VMNetworkAdapter -VMName Kirkland -PortMirroring Source
```

This example enables port mirroring for all virtual network adapters on virtual machine Kirkland.
When port mirroring is enabled, every packet sent or received by this virtual machine is copied and sent to a monitoring virtual machine.

### Example 3
```
PS C:\> Set-VMNetworkAdapter -VMName Bellevue -Name PM_Dest -PortMirroring Destination
```

This example configures the virtual network adapter named PM_Dest as the destination for port mirroring, which configures the virtual machine named Bellevue to monitor network traffic.
That is, a copy of every packet sent or received by a monitored virtual machine connected to the same virtual switch is sent to virtual machine Bellevue through virtual network adapter PM_Dest.

### Example 4
```
PS C:\> Get-VMNetworkAdapter -All | Set-VMNetworkAdapter -VmqWeight 100
```

This example enables VMQ and sets a weight of 100 on every virtual network adapter on the local host.

### Example 5
```
PS C:\> Get-VM Redmond | Set-VMNetworkAdapter -AllowTeaming On
```

This example configures NIC Teaming for all virtual network adapters of the virtual machine named Redmond.

### Example 6
```
PS C:\> Get-VMNetworkAdapter -VMName Redmond,Kirkland,Bellevue | Set-VMNetworkAdapter -MinimumBandwidthWeight 1
```

This example sets the same minimum bandwidth weight for all virtual network adapters of three virtual machines: Redmond, Kirkland, and Bellevue.
This configuration shares bandwidth equally among all of the virtual network adapters of these virtual machines.

## PARAMETERS

### -AllowTeaming
Specifies whether the virtual network adapter can be teamed with other network adapters connected to the same virtual switch.
The value can be **On** (allowed) or **Off** (disallowed).

```yaml
Type: OnOffState
Parameter Sets: (All)
Aliases:
Accepted values: On, Off

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
Parameter Sets: VMName, ManagementOS
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which features of the network adapter are to be configured.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName, ManagementOS
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
Parameter Sets: VMName, ManagementOS
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceNaming
Specifies whether this adapter uses device naming.

```yaml
Type: OnOffState
Parameter Sets: (All)
Aliases:
Accepted values: On, Off

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DhcpGuard
Specifies whether to drop DHCP messages from a virtual machine claiming to be a DHCP server.
Allowed values are **On**, which drops DHCP messages because the virtualized DHCP server is considered untrusted) or **Off**, which allows the message to be received because the virtualized DHCP server is considered to be trustworthy.

```yaml
Type: OnOffState
Parameter Sets: (All)
Aliases:
Accepted values: On, Off

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DynamicIPAddressLimit
Specifies the dynamic IP address limit, an integer.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DynamicMacAddress
Assigns a dynamically generated MAC address to the virtual network adapter..

```yaml
Type: SwitchParameter
Parameter Sets: VMName, ResourceObject, VMObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FixSpeed10G
Specifies whether the adapter uses fix speed of 10G.

```yaml
Type: OnOffState
Parameter Sets: (All)
Aliases:
Accepted values: On, Off

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPsecOffloadMaximumSecurityAssociation
Specifies the maximum number of security associations that can be offloaded to the physical network adapter that is bound to the virtual switch and that supports IPSec Task Offload.
Specify zero to disable the feature.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IeeePriorityTag
Specifies whether IEEE 802.1p tagged packets from the virtual machine should be trusted.
The value should be either **On** (trusted) or **Off** (not trusted).
If it is on, the IEEE 802.1p tagged packets will be let go as is.
If it is off, the priority value is reset to 0.

```yaml
Type: OnOffState
Parameter Sets: (All)
Aliases:
Accepted values: On, Off

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IovInterruptModeration
Specifies the interrupt moderation value for a single-root I/O virtualization (SR-IOV) virtual function assigned to a virtual network adapter.
Allowed values are **Default**, **Adaptive**, **Off**, **Low**, **Medium**, and **High**.
If **Default** is chosen, the value is determined by the physical network adapter vendor's setting.
If **Adaptive** is chosen, the interrupt moderation rate will be based on the runtime traffic pattern.

```yaml
Type: IovInterruptModerationValue
Parameter Sets: (All)
Aliases:
Accepted values: Default, Adaptive, Off, Low, Medium, High

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IovQueuePairsRequested
Specifies the number of hardware queue pairs to be allocated to an SR-IOV virtual function.
If receive-side scaling (RSS) is required, and if the physical network adapter that binds to the virtual switch supports RSS on SR-IOV virtual functions, then more than one queue pair is required.
Allowed values range from 1 to 4294967295.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IovWeight
Specifies whether single-root I/O virtualization (SR-IOV) is to be enabled on this virtual network adapter.
The relative weight sets the affinity of the virtual network adapter to the assigned SR-IOV virtual function.
The range of the value is from 0 through 100.
Specify 0 to disable SR-IOV on the virtual network adapter.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MacAddressSpoofing
Specifies whether virtual machines may change the source MAC address in outgoing packets to one not assigned to them.
Allowed values are **On** (allowing the virtual machine to use a different MAC address) and **Off** (allowing the virtual machine to use only the MAC address assigned to it).

```yaml
Type: OnOffState
Parameter Sets: (All)
Aliases:
Accepted values: On, Off

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementOS
Specifies the virtual network adapter in the management operating system to be configured.

```yaml
Type: SwitchParameter
Parameter Sets: ManagementOS
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MandatoryFeatureId
Specifies the unique identifiers of the virtual switch extension features that are required for this virtual network adapter to operate.

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

### -MaximumBandwidth
Specifies the maximum bandwidth, in bits per second, for the virtual network adapter.
The specified value is rounded to the nearest multiple of eight.
Specify zero to disable the feature.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumBandwidthAbsolute
Specifies the minimum bandwidth, in bits per second, for the virtual network adapter.
The specified value is rounded to the nearest multiple of eight.
A value larger than 100 Mbps is recommended.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumBandwidthWeight
Specifies the minimum bandwidth, in terms of relative weight, for the virtual network adapter.
The weight describes how much bandwidth to provide to the virtual network adapter relative to other virtual network adapters connected to the same virtual switch.
The range of the value is from 0 through 100.
Specify 0 to disable the feature.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name for the virtual network adapter.
The cmdlet changes the name to the value that you specify.

```yaml
Type: String
Parameter Sets: VMName, ManagementOS, VMObject
Aliases: VMNetworkAdapterName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotMonitoredInCluster
Indicates whether to not monitor the network adapter if the virtual machine that it belongs to is part of a cluster.
By default, network adapters for clustered virtual machines are monitored.

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

### -PacketDirectModerationCount
Specifies the number of packets to wait for before signaling an interrupt.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PacketDirectModerationInterval
Specifies the amount of time, in milliseconds, to wait before signaling an interrupt after a packet arrives.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PacketDirectNumProcs
Specifies the number of processors to use for virtual switch processing inside of the host.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the virtual network adapter to be configured.
This is a  **Microsoft.HyperV.PowerShell.VMInternalNetworkAdapter** object, if ManagementOS is specified; or a **Microsoft.HyperV.PowerShell.VMNetworkAdapter** object otherwise.

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

### -PortMirroring
Specifies the port mirroring mode for the network adapter to be configured.
Allowed values are **None**, **Source**, and **Destination**.
If a virtual network adapter is configured as **Source**, every packet it sends or receives is copied and forwarded to a virtual network adapter configured to receive the packets.
If a virtual network adapter is configured as **Destination**, it receives copied packets from the source virtual network adapter.
The source and destination virtual network adapters must be connected to the same virtual switch.
Specify **None** to disable the feature.

```yaml
Type: VMNetworkAdapterPortMirroringMode
Parameter Sets: (All)
Aliases:
Accepted values: None, Destination, Source

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourcePoolName
Specifies the name of the resource pool.

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

### -RouterGuard
Specifies whether to drop **Router Advertisement** and **Redirection** messages from unauthorized virtual machines.
The value can be either **On** or **Off**.
If **On** is specified, such messages are dropped.
If **Off** is specified, such messages are sent.

```yaml
Type: OnOffState
Parameter Sets: (All)
Aliases:
Accepted values: On, Off

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StaticMacAddress
Assigns a specific a MAC address to the virtual network adapter.

```yaml
Type: String
Parameter Sets: VMName, ResourceObject, VMObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StormLimit
Specifies the number of broadcast, multicast, and unknown unicast packets per second a virtual machine is allowed to send through the specified virtual network adapter.
Broadcast, multicast, and unknown unicast packets beyond the limit during that one second interval are dropped.
A value of zero (0) means there is no limit.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TestReplicaPoolName
This parameter applies only to virtual machines that are enabled for replication.
It specifies the name of the network resource pool that will be used by this virtual network adapter when its virtual machine is created during a test failover.

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

### -TestReplicaSwitchName
This parameter applies only to virtual machines that are enabled for replication.
It specifies the name of the virtual switch to which the virtual network adapter should be connected when its virtual machine is created during a test failover.

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

### -VM
Specifies the virtual machine that has the virtual network you want to configure.

```yaml
Type: VirtualMachine
Parameter Sets: VMObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine that has the virtual network adapteryou want to configure.

```yaml
Type: String
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMNetworkAdapter
Specifies the virtual network adapter.

```yaml
Type: VMNetworkAdapterBase
Parameter Sets: ResourceObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualSubnetId
Specifies the virtual subnet ID to use with Hyper-V Network Virtualization.
Allowed values range from 4096 to 16777215 (2^24 - 1), in addition to 0.
Use 0 to clear this parameter.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VmmqEnabled


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

### -VmmqQueuePairs


```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VmqWeight
Specifies whether virtual machine queue (VMQ) is to be enabled on the virtual network adapter.
. The relative weight describes the affinity of the virtual network adapter to use VMQ.
The range of value is from 0 through 100.
Specify 0 to disable VMQ on the virtual network adapter.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VrssEnabled


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

By default, this cmdlet doesn't return any output.

### Microsoft.HyperV.PowerShell.VMNetworkAdapter

When you use the **PassThru** parameter, this cmdlet returns a **Microsoft.HyperV.PowerShell.VMNetworkAdapter** object. 

### Microsoft.HyperV.PowerShell.VMInternalNetworkAdapter

When you use the **PassThru** and **-ManagementOS** parameters, this cmdlet returns a **Microsoft.HyperV.PowerShell.VMInternalNetworkAdapter** object.

## NOTES

## RELATED LINKS

