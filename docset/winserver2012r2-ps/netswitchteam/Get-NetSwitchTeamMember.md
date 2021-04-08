---
author: Kateyanne
description: 
external help file: MSFT_NetSwitchTeamMember.cdxml-help.xml
manager: jasgro
Module Name: NetSwitchTeam
ms.author: v-kaunu
ms.date: 10/29/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/netswitchteam/get-netswitchteammember?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetSwitchTeamMember
---

# Get-NetSwitchTeamMember

## SYNOPSIS
Gets the current network adapter members of a switch team.

## SYNTAX

```
Get-NetSwitchTeamMember [[-Name] <String[]>] [[-Team] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetSwitchTeamMember** cmdlet gets the current network adapter members of a switch team.
A switch team is a teaming solution where the failover and load balancing algorithms are implemented as part of the forward extension in a Hyper-V extensible switch.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>get-NetSwitchTeamMember -Team "MyTeam1" -Name "Ethernet 2"
```

This example fetches the member description for the member named Ethernet 2 of switch team named MyTeam1.

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
Specifies the name of the switch team member or an object that represents a part of a switch team.
The adapter names are the IfAlias names, such as Ethernet 3.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Team
Specifies the name of the switch team.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-NetSwitchTeamMember](./Add-NetSwitchTeamMember.md)

[Remove-NetSwitchTeamMember](./Remove-NetSwitchTeamMember.md)

