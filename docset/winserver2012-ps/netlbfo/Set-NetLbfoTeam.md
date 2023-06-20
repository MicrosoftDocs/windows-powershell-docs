---
external help file: NetLbfo_Cmdlets.xml
Module Name: NetLbfo
online version: https://learn.microsoft.com/powershell/module/netlbfo/set-netlbfoteam?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NetLbfoTeam

## SYNOPSIS
Sets parameters on the specified NIC team.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NetLbfoTeam [[-Name] <String[]>] [-AsJob] [-CimSession <CimSession[]>] [-LoadBalancingAlgorithm <LBAlgos>]
 [-PassThru] [-TeamingMode <TeamingModes>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NetLbfoTeam [-AsJob] [-CimSession <CimSession[]>] [-LoadBalancingAlgorithm <LBAlgos>]
 [-MemberOfTheTeam <CimInstance>] [-PassThru] [-TeamingMode <TeamingModes>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Set-NetLbfoTeam [-AsJob] [-CimSession <CimSession[]>] [-LoadBalancingAlgorithm <LBAlgos>] [-PassThru]
 [-TeamingMode <TeamingModes>] [-ThrottleLimit <Int32>] -InputObject <CimInstance[]>
```

### UNNAMED_PARAMETER_SET_4
```
Set-NetLbfoTeam [-AsJob] [-CimSession <CimSession[]>] [-LoadBalancingAlgorithm <LBAlgos>] [-PassThru]
 [-TeamingMode <TeamingModes>] [-TeamNicForTheTeam <CimInstance>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Set-NetLbfoTeam** cmdlet sets the **TeamingMode** or **LoadBalancingAlgorithm** parameters  on the specified NIC team.

You need administrator privileges to use **Set-NetLbfoTeam**.

## EXAMPLES

### Example 1: Set the teaming mode
```
PS C:\>Set-NetLbfoTeam -Name Team1 -TeamingMode LACP
```

This command sets the teaming mode of the team named Team1 to LACP.

### Example 2: Set the load balancing algorithm
```
PS C:\>Set-NetLbfoTeam -Name Team1 -LoadBalancingAlgorithm HyperVPorts
```

This command sets the load balancing algorithm of the team named Team1 to HyperVPorts.

### Example 3: Set the teaming mode and load balancing algorithm
```
PS C:\>Set-NetLbfoTeam -Name Team1 -TeamingMode LACP -LoadBalancingAlgorithm HyperVPorts
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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the object which contains the NIC team parameters to set.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LoadBalancingAlgorithm
Specifies the load balancing algorithm the NIC team uses to distribute network traffic between the interfaces.

You can specify one of the following four load balancing algorithms:

**TransportPorts**: Uses the source and destination TCP ports and the IP addresses to create a hash, and then assigns the packets that have the matching hash value to one of the available interfaces.

**IPAddresses**: Uses the source and destination IP addresses to create a hash, and then assigns the packets that have the matching hash value to one of the available interfaces.

**MacAddresses**: Uses the source and destination MAC addresses to create a hash and then assigns the packets that have the matching hash value to one of the available interfaces.

**HyperVPort**: Distributes network traffic based on the source virtual machine Hyper-V switch port identifier.

```yaml
Type: LBAlgos
Parameter Sets: (All)
Aliases: lba

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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TeamingMode
Specifies the mode of the NIC teaming.
You can specify one of the following three teaming modes:

**LACP**: Requires configuration on both the switch and the host to identify which links form the team.
Uses the Link Aggregation Control Protocol (LACP) to identify links that are connected between the host and a given switch.

**Static**: Requires configuration on both the switch and the host to identify which links form the team.

**SwitchIndependent**: Specifies that a network switch configuration is not needed for the NIC team.
Because the network switch is not configured to know about the NIC teaming, the team members can be connected to different switches.

```yaml
Type: TeamingModes
Parameter Sets: (All)
Aliases: tm

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

