---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetSwitchTeam.cdxml-help.xml
Module Name: NetSwitchTeam
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netswitchteam/new-netswitchteam?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetSwitchTeam
---

# New-NetSwitchTeam

## SYNOPSIS
Creates a switch team.

## SYNTAX

```
New-NetSwitchTeam [-Name] <String> [-TeamMembers] <String[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetSwitchTeam** cmdlet creates a switch team.
A switch team must have a name for the team and must be created with one or more members, or network adapters.

The network switch team is a team that is controlled by a Hyper-V extensible switch forwarding extension.
No other cmdlets can be used to manage a switch team and the Network Switch Team Cmdlets in Windows PowerShell must not be used to manage standard, or non-switch, network adapter teams.

## EXAMPLES

### Example 1: Create a team
```
PS C:\>New-NetSwitchTeam -Name "SwitchTeam01" -TeamMembers "Ethernet 2","Ethernet 3"
```

This command creates a team named SwitchTeam01 that has two network adapter members.

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
Specifies the name of the switch team being created.
The name must be a unique team name that does not exist as either a switch team or Load-Balancing/Fail-Over team name.

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
Specifies one or more network adapters to add as members of the team.
A new team must have at least one member upon creation.
The network adapters must already exist and not be part of another team.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NetSwitchTeam](./Get-NetSwitchTeam.md)

[Remove-NetSwitchTeam](./Remove-NetSwitchTeam.md)

[Rename-NetSwitchTeam](./Rename-NetSwitchTeam.md)

