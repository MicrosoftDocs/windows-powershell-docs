---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetLbfoTeamMember.cdxml-help.xml
Module Name: NetLbfo
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netlbfo/get-netlbfoteammember?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetLbfoTeamMember
---

# Get-NetLbfoTeamMember

## SYNOPSIS
Gets network adapters that are members of a NIC team.

## SYNTAX

### ByNameAndOrTeam (Default)
```
Get-NetLbfoTeamMember [[-Name] <String[]>] [[-Team] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByTeamOfTheMember
```
Get-NetLbfoTeamMember [-TeamOfTheMember <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetLbfoTeamMember** cmdlet gets all network adapters (team members) of all NIC teams.
You can also use **Get-NetLbfoTeamMember** to get the network adapters for a specified NIC team, and then use that object as input to other cmdlets.

## EXAMPLES

### Example 1: Get members of a NIC team
```
PS C:\> Get-NetLbfoTeamMember -Team "Team1"
```

This command retrieves a list of team members for the NIC team named Team1.

### Example 2: Get all members of all NIC teams
```
PS C:\> Get-NetLbfoTeamMember
```

This command retrieves a list of all team members of all NIC teams on the system.

### Example 3: Get team members via associations
```
PS C:\> Get-NetLbfoTeam -Name "Team1" | Get-NetLbfoTeamMember

Or
PS C:\> $teamObj = Get-NetLbfoTeam -Name "Team1"
PS C:\> Get-NetLbfoTeamMember -TeamOfTheMember $teamObj
```

This command retrieves a list of all team members belonging to team named Team1.

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

### -Name
Specifies an array of names of team members.
Wildcard characters are acceptable.

```yaml
Type: String[]
Parameter Sets: ByNameAndOrTeam
Aliases: ifAlias, InterfaceAlias

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Team
Specifies the NIC team name (or wildcard pattern) for which the user wants to enumerate the members.
If no team parameter is present, it returns all members specified by *Name* parameter from all teams on the system.

```yaml
Type: String[]
Parameter Sets: ByNameAndOrTeam
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TeamOfTheMember
Specifies the NIC team object whose associated member objects you want to get.

```yaml
Type: CimInstance
Parameter Sets: ByTeamOfTheMember
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet takes no input objects.

## OUTPUTS

### MSFT_NetLbfoTeamMember[]
This cmdlet returns an array of **MSFT_NetLbfoTeamMember** objects.

## NOTES

## RELATED LINKS

[Add-NetLbfoTeamMember](./Add-NetLbfoTeamMember.md)

[Remove-NetLbfoTeamMember](./Remove-NetLbfoTeamMember.md)

[Set-NetLbfoTeamMember](./Set-NetLbfoTeamMember.md)

