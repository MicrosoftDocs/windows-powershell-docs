---
external help file: NetSwitchTeam_Cmdlets.xml
Module Name: NetSwitchTeam
online version: https://learn.microsoft.com/powershell/module/netswitchteam/remove-netswitchteammember?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-NetSwitchTeamMember

## SYNOPSIS
Removes a network adapter member from a switch team.

## SYNTAX

```
Remove-NetSwitchTeamMember [-Name] <String> [-Team] <String> [-AsJob] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Remove-NetSwitchTeamMember** cmdlet removes a network adapter team member from the specified switch team.
The specified switch team must be an existing switch team.
The member designated must exist in the specified switch team.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-NetSwitchTeamMember -Team "MyTeam1" -Name "Ethernet 2"
```

This example will remove the network adapter named Ethernet 2 from the switch team named MyTeam1.

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
Specifies the name of the switch team member or an object that represents a part of a switch team.
The adapter names are the IfAlias names, such as Ethernet 2.

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

### -Team
Specifies the name of switch team from which to remove the network adapter.
The switch team must already exist and must be a switch team.

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

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-NetSwitchTeamMember](./Add-NetSwitchTeamMember.md)

[Get-NetSwitchTeamMember](./Get-NetSwitchTeamMember.md)

