---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetLbfoTeam.cdxml-help.xml
Module Name: NetLbfo
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netlbfo/new-netlbfoteam?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetLbfoTeam
---

# New-NetLbfoTeam

## SYNOPSIS
Creates a new NIC team.

## SYNTAX

```
New-NetLbfoTeam [-Name] <String> [-TeamMembers] <WildcardPattern[]> [[-TeamNicName] <String>]
 [[-TeamingMode] <TeamingModes>] [[-LoadBalancingAlgorithm] <LBAlgos>] [[-LacpTimer] <LacpTimers>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetLbfoTeam** cmdlet creates a new NIC team that consists of one or more network adapters.
Teaming network adapters of different speeds is not supported.
You can create a team with network adapters of different speeds, but the network traffic distribution algorithms do not take the speed of each network adapter into consideration when distributing traffic.

When you create a team, you can specify additional properties such as TeamingMode and LoadBalancingAlgorithm.

You must have administrator rights to use **New-NetLbfoTeam**.

## EXAMPLES

### Example 1: Create a team
```
PS C:\> New-NetLbfoTeam -Name "Team1" -TeamMembers "NIC1","NIC2"
```

This command creates a team named Team1 with two team members named NIC1 and NIC2.

### Example 2: Create a team with specified properties
```
PS C:\> New-NetLbfoTeam -Name "Team1" -TeamMembers "NIC1","NIC2" -TeamingMode LACP -LoadBalancingAlgorithm HyperVPort
```

This command creates a team named Team1 that consists of two team members named NIC1 and NIC2.
The teaming mode is set to LACP and the load balancing algorithm is set to HyperVPorts.

### Example 3: Create a team in a virtual machine
```
PS C:\> Set-VMNetworkAdapter -VMName <VMname> -AllowTeaming On
PS C:\> New-NetLbfoTeam -Name "Team2" -TeamMembers "NIC1","NIC2"
```

This set of commands allows teaming in virtual machines by using the *AllowTeaming* parameter of the Set-VMNetworkAdapter cmdlet and then creates a team named Team2 in the virtual machine specified by *VMName*.
You must run the following command in the host (parent partition) with administrator rights.

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

### -LacpTimer
Specifies how often inter-connected devices exchange LACP protocol data units (PDUs) or control messages.

```yaml
Type: LacpTimers
Parameter Sets: (All)
Aliases: lt
Accepted values: Slow, Fast

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancingAlgorithm
Specifies the load-balancing algorithm the new team uses to distribute network traffic between the interfaces.

You can specify one of the following load balancing algorithms:

- Dynamic.
Uses the source and destination TCP ports and the IP addresses to create a hash for outbound traffic.  Moves outbound streams from team member to team member as needed to balance team member utilization.
When you specify this algorithm with the *TeamingMode* parameter and the SwitchIndependent value, inbound traffic is routed to a particular team member.

- TransportPorts.
Uses the source and destination TCP ports and the IP addresses to create a hash and then assigns the packets that have the matching hash value to one of the available interfaces.
When you specify this algorithm with the *TeamingMode* parameter and the SwitchIndependent value, all inbound traffic arrives on the primary team member.

- IPAddresses.
Uses the source and destination IP addresses to create a hash and then assigns the packets that have the matching hash value to one of the available interfaces.
When you specify this algorithm with the *TeamingMode* parameter and the SwitchIndependent value, all inbound traffic arrives on the primary team member.

- MacAddresses.
Uses the source and destination MAC addresses to create a hash and then assigns the packets that have the matching hash value to one of the available interfaces.
When you specify this algorithm with the *TeamingMode* parameter and the SwitchIndependent value, all inbound traffic arrives on the primary team member.

- HyperVPort.
Distributes network traffic based on the source virtual machine Hyper-V switch port identifier.
When you specify this algorithm with the *TeamingMode* parameter and the SwitchIndependent value, inbound traffic is routed to the same team member as the switch port's outgoing traffic.

```yaml
Type: LBAlgos
Parameter Sets: (All)
Aliases: lba
Accepted values: TransportPorts, IPAddresses, MacAddresses, HyperVPort, Dynamic

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the new NIC team.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TeamMembers
Specifies the names of the network adapters that are members of the new team.
Specify multiple network adapter names (or wildcard patterns) separated by a comma.

```yaml
Type: WildcardPattern[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TeamNicName
Specifies the name of the new team interface.
This is the name used to reference the teamed network adapters.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TeamingMode
Specifies the mode of the NIC teaming.
You can specify one of the following three teaming modes:

- LACP.
Uses the IEEE 802.1ax Link Aggregation Control Protocol (LACP) to dynamically identify links that are connected between the host and a given switch.
(This protocol was formerly known as IEEE 802.3ad draft.)

- Static.
Requires configuration on both the switch and the host to identify which links form the team.

- SwitchIndependent.
Specifies that a network switch configuration is not needed for the NIC team.
Because the network switch is not configured to know about the interface teaming, the team interfaces can be connected to different switches.

```yaml
Type: TeamingModes
Parameter Sets: (All)
Aliases: tm
Accepted values: Static, SwitchIndependent, Lacp

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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
This cmdlet takes no input objects.

## OUTPUTS

### MSFT_NetLbfoTeam
This cmdlet produces an **MSFT_NetLbfoTeam** object, corresponding to the newly created team.

## NOTES

## RELATED LINKS

[Get-NetLbfoTeam](./Get-NetLbfoTeam.md)

[Remove-NetLbfoTeam](./Remove-NetLbfoTeam.md)

[Rename-NetLbfoTeam](./Rename-NetLbfoTeam.md)

[Set-NetLbfoTeam](./Set-NetLbfoTeam.md)
