---
external help file: MSFT_NetLbfoTeamMember.cdxml-help.xml
Module Name: NetLbfo
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/netlbfo/add-netlbfoteammember?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-NetLbfoTeamMember
---

# Add-NetLbfoTeamMember

## SYNOPSIS
Adds a new member (network adapter) to a specified NIC team.

## SYNTAX

```
Add-NetLbfoTeamMember [-Name] <WildcardPattern> [-Team] <String> [[-AdministrativeMode] <AdminModes>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-NetLbfoTeamMember** cmdlet adds a new network adapter as a member to the specified team.
You can use the **AdministrativeMode** parameter to specify the initial role of the new team member.

## EXAMPLES

### Example 1: Add a new team member
```
PS C:\> Add-NetLbfoTeamMember -Name NIC1 -Team Team1
```

This command adds a new member named NIC1 to the specified team named Team1.

### Example 2: Add a new team member with initial status
```
PS C:\> Add-NetLbfoTeamMember -Name NIC2 -Team Team2 -AdministrativeMode Standby
```

This command adds a new member named NIC2 to the specified team named Team2 with the initial status Standby.

### Example 3: Add new team members using wildcard pattern
```
PS C:\> Add-NetLbfoTeamMember -Name NIC* -Team Team1
```

This command adds new members whose name starts with NIC to the specified team named Team1.

## PARAMETERS

### -AdministrativeMode
Specifies the initial role of the new member (network adapter).

You can specify one of the following two status options:

**Active**: Allows the team member to participate in the NIC team.
By default, the initial role of the team member is Active.

**Standby**: Places the member in a standby state where it does not participate in the team.
The team member will be automatically moved to Active state if any other member of the team fails.

At most one member in a team can be in Standby mode.

```yaml
Type: AdminModes
Parameter Sets: (All)
Aliases: am
Accepted values: Active, Standby

Required: False
Position: 2
Default value: Active
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name (Interface Alias or Connection Name) of the network adapter to add.

```yaml
Type: WildcardPattern
Parameter Sets: (All)
Aliases: ifAlias, InterfaceAlias

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Team
Specifies the name of the NIC team to which to add the new network adapter.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
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
This cmdlet returns an array of **MSFT_NetLbfoTeamMember** objects consisting of the newly added member network adapter objects to the team.

## NOTES

## RELATED LINKS

[Get-NetLbfoTeamMember](./Get-NetLbfoTeamMember.md)

[Set-NetLbfoTeamMember](./Set-NetLbfoTeamMember.md)

[Remove-NetLbfoTeamMember](./Remove-NetLbfoTeamMember.md)

