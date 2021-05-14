---
external help file: MSFT_NetLbfoTeam.cdxml-help.xml
Module Name: NetLbfo
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/netlbfo/set-netlbfoteam?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetLbfoTeam
---

# Set-NetLbfoTeam

## SYNOPSIS
Sets parameters on the specified NIC team.

## SYNTAX

### ByName (Default)
```
Set-NetLbfoTeam [[-Name] <String[]>] [-TeamingMode <TeamingModes>] [-LoadBalancingAlgorithm <LBAlgos>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByMemberOfTheTeam
```
Set-NetLbfoTeam [-MemberOfTheTeam <CimInstance>] [-TeamingMode <TeamingModes>]
 [-LoadBalancingAlgorithm <LBAlgos>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByTeamNicForTheTeam
```
Set-NetLbfoTeam [-TeamNicForTheTeam <CimInstance>] [-TeamingMode <TeamingModes>]
 [-LoadBalancingAlgorithm <LBAlgos>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetLbfoTeam -InputObject <CimInstance[]> [-TeamingMode <TeamingModes>] [-LoadBalancingAlgorithm <LBAlgos>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetLbfoTeam** cmdlet sets the **TeamingMode** or **LoadBalancingAlgorithm** parameters  on the specified NIC team.

You need administrator privileges to use **Set-NetLbfoTeam**.

## EXAMPLES

### Example 1: Set the teaming mode
```
PS C:\> Set-NetLbfoTeam -Name Team1 -TeamingMode LACP
```

This command sets the teaming mode of the team named Team1 to LACP.

### Example 2: Set the load balancing algorithm
```
PS C:\> Set-NetLbfoTeam -Name Team1 -LoadBalancingAlgorithm HyperVPorts
```

This command sets the load balancing algorithm of the team named Team1 to HyperVPorts.

### Example 3: Set the teaming mode and load balancing algorithm
```
PS C:\> Set-NetLbfoTeam -Name Team1 -TeamingMode LACP -LoadBalancingAlgorithm HyperVPorts
```

This command sets the teaming mode and load balancing algorithm of the team named Team1 at the same time.
The teaming mode is set to LACP and the load balancing algorithm is set to HyperVPorts.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -InputObject
Specifies the object which contains the NIC team parameters to set.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LoadBalancingAlgorithm
Specifies the load balancing algorithm the NIC team uses to distribute network traffic between the interfaces.
You can specify one of the following load balancing algorithms:

-- **Dynamic**:  Uses the source and destination TCP ports and the IP addresses to create a hash for outbound traffic.  Moves outbound streams from team member to team member as needed to balance team member utilization.  When you specify this algorithm with the **TeamingMode** parameter and the **SwitchIndependent** value, inbound traffic is routed to a particular team member.
-- **TransportPorts**: Uses the source and destination TCP ports and the IP addresses to create a hash, and then assigns the packets that have the matching hash value to one of the available interfaces. When you specify this algorithm with the **TeamingMode** parameter and the **SwitchIndependent** value all inbound traffic arrives on the primary team member.
-- **IPAddresses**: Uses the source and destination IP addresses to create a hash, and then assigns the packets that have the matching hash value to one of the available interfaces. When you specify this algorithm with the **TeamingMode** parameter and the **SwitchIndependent** value, all inbound traffic arrives on the primary team member.
-- **MacAddresses**: Uses the source and destination MAC addresses to create a hash and then assigns the packets that have the matching hash value to one of the available interfaces. When you specify this algorithm with the **TeamingMode** parameter and the **SwitchIndependent** value, all inbound traffic arrives on the primary team member.
-- **HyperVPort**: Distributes network traffic based on the source virtual machine Hyper-V switch port identifier. When you specify this algorithm with the **TeamingMode** parameter and the **SwitchIndependent** value, inbound traffic is routed to the same team member as the switch port's outgoing traffic.

```yaml
Type: LBAlgos
Parameter Sets: (All)
Aliases: lba
Accepted values: TransportPorts, IPAddresses, MacAddresses, HyperVPort, Dynamic

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemberOfTheTeam
Specifies the network adapter name for which to modify the parameters.

```yaml
Type: CimInstance
Parameter Sets: ByMemberOfTheTeam
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the NIC team to modify.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
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

### -TeamNicForTheTeam
Specifies the team interface whose associated NIC team is to be modified.

```yaml
Type: CimInstance
Parameter Sets: ByTeamNicForTheTeam
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TeamingMode
Specifies the mode of the NIC teaming.
You can specify one of the following teaming modes:

-- **LACP**: Requires configuration on both the switch and the host to identify which links form the team. Uses the Link Aggregation Control Protocol (LACP) to identify links that are connected between the host and a given switch.
-- **Static**: Requires configuration on both the switch and the host to identify which links form the team.
-- **SwitchIndependent**: Specifies that a network switch configuration is not needed for the NIC team. Because the network switch is not configured to know about the NIC teaming, the team members can be connected to different switches.

```yaml
Type: TeamingModes
Parameter Sets: (All)
Aliases: tm
Accepted values: Static, SwitchIndependent, Lacp

Required: False
Position: Named
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet takes no input objects.

## OUTPUTS

### MSFT_NetLbfoTeam
By default, this cmdlet produces no output.
If the **PassThru** parameter is specified, the cmdlet returns the updated **MSFT_NetLbfoTeam** object.

## NOTES

## RELATED LINKS

[New-NetLbfoTeam](./New-NetLbfoTeam.md)

[Get-NetLbfoTeam](./Get-NetLbfoTeam.md)

[Rename-NetLbfoTeam](./Rename-NetLbfoTeam.md)

[Remove-NetLbfoTeam](./Remove-NetLbfoTeam.md)

