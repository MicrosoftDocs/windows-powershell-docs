---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetLbfoTeamNic.cdxml-help.xml
Module Name: NetLbfo
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netlbfo/get-netlbfoteamnic?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetLbfoTeamNic
---

# Get-NetLbfoTeamNic

## SYNOPSIS
Gets a list of team interfaces.

## SYNTAX

### ByNameOrTeam (Default)
```
Get-NetLbfoTeamNic [[-Name] <String[]>] [[-Team] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByTeamOfTheTeamNic
```
Get-NetLbfoTeamNic [-TeamOfTheTeamNic <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetLbfoTeamNic** cmdlet gets a list of team interfaces as specified by the input parameters.

## EXAMPLES

### Example 1: Get a list of team interfaces associated with Team1
```
PS C:\>Get-NetLbfoTeamNic -Team "Team1"

Or
PS C:\> $teamObj = Get-NetLbfoTeam -Name "Team1"
PS C:\> Get-NetLbfoTeamNic -Team $teamObj
```

This command gets a list of team interfaces for the team named Team1.

### Example 2: Get a list of team interfaces by name
```
PS C:\> Get-NetLbfoTeamNic -Name "*VLAN*" -Team "T*"
```

This command gets a list of team interfaces whose name contains VLAN in any NIC team whose name starts with T.

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
Specifies the name (or wildcard pattern) of the team interface.

```yaml
Type: String[]
Parameter Sets: ByNameOrTeam
Aliases: ifAlias, InterfaceAlias

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Team
Specifies the name of the NIC team for which the user wants to enumerate the team interfaces.

```yaml
Type: String[]
Parameter Sets: ByNameOrTeam
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TeamOfTheTeamNic
Specifies the NIC team object whose team interfaces you want to enumerate.

```yaml
Type: CimInstance
Parameter Sets: ByTeamOfTheTeamNic
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

### MSFT_NetLbfoTeamNic
This cmdlet produces an array of **MSFT_NetLbfoTeamNic** objects corresponding to the query.

## NOTES

## RELATED LINKS

[Add-NetLbfoTeamNic](./Add-NetLbfoTeamNic.md)

[Remove-NetLbfoTeamNic](./Remove-NetLbfoTeamNic.md)

[Set-NetLbfoTeamNic](./Set-NetLbfoTeamNic.md)

