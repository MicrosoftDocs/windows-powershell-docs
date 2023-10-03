---
external help file: NetSwitchTeam_Cmdlets.xml
Module Name: NetSwitchTeam
online version: https://learn.microsoft.com/powershell/module/netswitchteam/get-netswitchteam?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetSwitchTeam

## SYNOPSIS
Gets the extensible switch team.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NetSwitchTeam [[-Name] <String[]>] [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NetSwitchTeam [-AsJob] [-CimSession <CimSession[]>] [-Member <CimInstance>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NetSwitchTeam** cmdlet gets the extensible switch team.
If no parameter is specified, then this cmdlet returns all of the switch teams on the server.
The name may contain wildcard characters (`*`) for matching.
For example, `T*1` would match all of the team names beginning with `T` and ending with `1`.
Alternately the switch team may be identified by a switch team member.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-NetSwitchTeam -Name "MyTeam1"
```

This example gets the switch team named MyTeam1.

### EXAMPLE 2
```
PS C:\> Get-NetSwitchTeam -Name "MyT*"
```

This example gets all of the switch teams with the name with the wildcard character matching MyT*.

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

### -Member
Specifies the member object of a network adapter in a switch team.
This parameter is used instead of the switch team name.

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
Specifies the name of the extensible switch team.
If no parameter is supplied, then this cmdlet returns all of the teams on the server. 

This parameter may contain wildcard characters (`*`) for matching.
For example, `T*1` would match all of the team names beginning with `T` and ending with `1`.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[New-NetSwitchTeam](./New-NetSwitchTeam.md)

[Remove-NetSwitchTeam](./Remove-NetSwitchTeam.md)

[Rename-NetSwitchTeam](./Rename-NetSwitchTeam.md)

