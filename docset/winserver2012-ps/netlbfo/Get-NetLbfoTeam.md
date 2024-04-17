---
external help file: NetLbfo_Cmdlets.xml
Module Name: NetLbfo
online version: https://learn.microsoft.com/powershell/module/netlbfo/get-netlbfoteam?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetLbfoTeam

## SYNOPSIS
Retrieves a list of NIC teams on the system, as specified by the input parameters.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NetLbfoTeam [[-Name] <String[]>] [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NetLbfoTeam [-AsJob] [-CimSession <CimSession[]>] [-TeamNicForTheTeam <CimInstance>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-NetLbfoTeam [-AsJob] [-CimSession <CimSession[]>] [-MemberOfTheTeam <CimInstance>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NetLbfoTeam** cmdlet retrieves the list of all available NIC teams on the system.

You can retrieve the list of NIC teams by specifying the name or name pattern of the team.
You can also use **Get-NetLbfoTeam** to retrieve the team associated with a team interface or a team member (network adapter).

## EXAMPLES

### Example 1: Get a specific team
```
PS C:\>Get-NetLbfoTeam -Name Team1
```

This command retrieves a NIC team named Team1.

### Example 2: Get the list of all teams whose name starts with 'T' and then remove
```
PS C:\>Get-NetLbfoTeam -Name T*| Remove-NetLbfoTeam
```

This command retrieves the list of teams whose name starts with T using **Get-NetLbfoTeam**.
A pipeline operator (|) sends all the teams to Remove-NetLbfoTeam which removes them.

### Example 3: Get the team associated with a particular member network adapter
```
PS C:\>Get-NetLbfoTeamMember NIC1 | Get-NetLbfoTeam


Or


PS C:\>$mObj = Get-NetLbfoTeamMember NIC1



PS C:\>Get-NetLbfoTeam -MemberOfTheTeam $mObj
```

This command retrieves the NIC team associated with a particular member network adapter named NIC1 using **Get-NetLbfoTeam**.

### Example 4: Get the team associated with a particular team interface
```
PS C:\>Get-NetLbfoTeamNic 'Team1 - VLAN 42' | Get-NetLbfoTeam


Or


PS C:\>$tNicObj = Get-NetLbfoTeamNic 'Team1 - VLAN 42'



PS C:\>Get-NetLbfoTeam -TeamNicForTheTeam $tNicObj
```

This command retrieves the NIC team associated with a particular team interface named Team1 - VLAN 42 using **Get-NetLbfoTeam**.

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

### -MemberOfTheTeam
Specifies the member network adapter name to retrieve the associated NIC team.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name (or name wildcard pattern) of the NIC team for which to retrieve information.

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

### -TeamNicForTheTeam
Specifies the team interface to retrieve the associated NIC team.

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
This cmdlet returns an array of **MSFT_NetLbfoTeam** objects containing the teams that match the query.

## NOTES

## RELATED LINKS

[New-NetLbfoTeam](./New-NetLbfoTeam.md)

[Remove-NetLbfoTeam](./Remove-NetLbfoTeam.md)

[Rename-NetLbfoTeam](./Rename-NetLbfoTeam.md)

[Set-NetLbfoTeam](./Set-NetLbfoTeam.md)

