---
author: Kateyanne
external help file: NetLbfo_Cmdlets.xml
manager: dansimp
Module Name: NetLbfo
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/netlbfo/get-netlbfoteamnic?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetLbfoTeamNic

## SYNOPSIS
Retrieves a list of team interfaces.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NetLbfoTeamNic [[-Name] <String[]>] [[-Team] <String[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NetLbfoTeamNic [-AsJob] [-CimSession <CimSession[]>] [-TeamOfTheTeamNic <CimInstance>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NetLbfoTeamNic** cmdlet retrieves a list of team interfaces as specified by the input parameters.

## EXAMPLES

### Example 1: Get a list of team interfaces associated with Team1
```
PS C:\>Get-NetLbfoTeamNic -Team Team1


Or
PS C:\>$teamObj = Get-NetLbfoTeam -Name 'Team1'

PS C:\>Get-NetLbfoTeamNic -TeamOfTheTeamNic $teamObj
```

This command retrieves a list of team interfaces for the specified team named Team1.

### Example 2: Get a list of team interfaces by name
```
PS C:\>Get-NetLbfoTeamNic -Name *VLAN* -Team T*
```

This command retrieves a list of team interfaces whose name contains "VLAN" in any NIC team whose name starts with T.

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
Specifies the name (or wildcard pattern) of the team interface.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: ifAlias, InterfaceAlias

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Team
Specifies the name of the NIC team for which the user wants to enumerate the team interfaces.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TeamOfTheTeamNic
Specifies the NIC team object whose team interfaces are to be enumerated.

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

### MSFT_NetLbfoTeamNic
This cmdlet produces an array of **MSFT_NetLbfoTeamNic** objects corresponding to the query.

## NOTES

## RELATED LINKS

[Add-NetLbfoTeamNic](./Add-NetLbfoTeamNic.md)

[Remove-NetLbfoTeamNic](./Remove-NetLbfoTeamNic.md)

[Set-NetLbfoTeamNic](./Set-NetLbfoTeamNic.md)

