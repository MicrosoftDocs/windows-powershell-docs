---
external help file: NetLbfo_Cmdlets.xml
Module Name: NetLbfo
online version: https://docs.microsoft.com/powershell/module/netlbfo/add-netlbfoteammember?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-NetLbfoTeamMember

## SYNOPSIS
Adds a new member (network adapter) to a specified NIC team.

## SYNTAX

```
Add-NetLbfoTeamMember [-Name] <WildcardPattern> [-Team] <String> [[-AdministrativeMode] <AdminModes>] [-AsJob]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Add-NetLbfoTeamMember** cmdlet adds a new network adapter as a member to the specified team.
You can use the **AdministrativeMode** parameter to specify the initial role of the new team member.

## EXAMPLES

### Example 1: Add a new team member
```
PS C:\>Add-NetLbfoTeamMember -Name NIC1 -Team Team1
```

This command adds a new member named NIC1 to the specified team named Team1.

### Example 2: Add a new team member with initial status
```
PS C:\>Add-NetLbfoTeamMember -Name NIC2 -Team Team2 -AdministrativeMode Standby
```

This command adds a new member named NIC2 to the specified team named Team2 with the initial status Standby.

### Example 3: Add new team members using wildcard pattern
```
PS C:\>Add-NetLbfoTeamMember -Name NIC* -Team Team1
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

Required: False
Position: 3
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
Aliases: 

Required: False
Position: Named
Default value: None
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
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Team
Specifies the name of the NIC team to which to add the new network adapter.

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
This cmdlet takes no input objects.

## OUTPUTS

### MSFT_NetLbfoTeamMember
This cmdlet returns an array of **MSFT_NetLbfoTeamMember** objects consisting of the newly added member network adapter objects to the team.

## NOTES

## RELATED LINKS

[Get-NetLbfoTeamMember](./Get-NetLbfoTeamMember.md)

[Set-NetLbfoTeamMember](./Set-NetLbfoTeamMember.md)

[Remove-NetLbfoTeamMember](./Remove-NetLbfoTeamMember.md)

