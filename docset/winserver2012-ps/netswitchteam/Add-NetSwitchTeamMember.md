---
external help file: NetSwitchTeam_Cmdlets.xml
Module Name: NetSwitchTeam
online version: https://docs.microsoft.com/powershell/module/netswitchteam/add-netswitchteammember?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-NetSwitchTeamMember

## SYNOPSIS
Adds a network adapter member to an existing switch team.

## SYNTAX

```
Add-NetSwitchTeamMember [-Name] <String> [-Team] <String> [-AsJob] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Add-NetSwitchTeamMember** cmdlet adds a network adapter member to an existing switch team.
The switch team algorithms are part of the forward extension in a Hyper-V extensible switch.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Add-NetSwitchTeamMember -Team "SwitchTeam1" -Name "Ethernet 2"
```

This example adds the network adapter named Ethernet 2 as a member of team named SwitchTeam1.

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

### -Name
Specifies one or more names of one or more network adapters to be added to the switch team.
Wildcard characters are allowed.
Network adapter names are the IfAlias names, such as Ethernet 3.
Only wired adapters that are not part of another team, switch team, or LBFO team can be added.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Team
Specifies the name of the switch team to which to add a network adapter.
The switch team must already exist. 

The team name cannot be a NetLbfo team name.
Use the NetLbfoTeam cmdlets for a NetLbfo team.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NetSwitchTeamMember](./Get-NetSwitchTeamMember.md)

[Remove-NetSwitchTeamMember](./Remove-NetSwitchTeamMember.md)

