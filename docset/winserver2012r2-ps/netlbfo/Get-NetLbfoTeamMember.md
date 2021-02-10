---
external help file: MSFT_NetLbfoTeamMember.cdxml-help.xml
Module Name: NetLbfo
online version: 
schema: 2.0.0
title: Get-NetLbfoTeamMember
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: ABCF968F-F925-47B0-844B-C6E05EB996C9
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-NetLbfoTeamMember

## SYNOPSIS
Retrieves a list of network adapters that are members of a NIC team, as specified by the input parameters.

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
The **Get-NetLbfoTeamMember** cmdlet retrieves the list of all network adapters (team members) of all NIC teams.
You can also use **Get-NetLbfoTeamMember** to retrieve a list of network adapters for the specified NIC team, and then use that information as input to the other cmdlets.

## EXAMPLES

### Example 1: Get a list of team members
```
PS C:\> Get-NetLbfoTeamMember -Team Team1
```

This command retrieves a list of team members for the specified NIC team named Team1.

### Example 2: Get a list of all team members
```
PS C:\> Get-NetLbfoTeamMember
```

This command retrieves a list of all team members of all NIC teams on the system.

### Example 3: Get a list of all team members via associations
```
PS C:\> Get-NetLbfoTeam -Name Team1 | Get-NetLbfoTeamMember

Or
PS C:\> $teamObj = Get-NetLbfoTeam -Name Team1
PS C:\> Get-NetLbfoTeamMember -TeamOfTheMember $teamObj
```

This command retrieves a list of all team members belonging to team named Team1.

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

### -Name
Specifies the name (or wildcard pattern of the name) of a team member whose details need to be retrieved.

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
If no team parameter is present, it returns all members specified by **Name** parameter from all teams on the system.

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
Specifies the NIC team object whose associated member objects are to be retrieved.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet takes no input objects.

## OUTPUTS

### MSFT_NetLbfoTeamMember
This cmdlet produces an array of **MSFT_NetLbfoTeamMember** objects corresponding to the query.

## NOTES

## RELATED LINKS

[Add-NetLbfoTeamMember](./Add-NetLbfoTeamMember.md)

[Remove-NetLbfoTeamMember](./Remove-NetLbfoTeamMember.md)

[Set-NetLbfoTeamMember](./Set-NetLbfoTeamMember.md)

