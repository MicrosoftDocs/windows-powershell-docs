---
external help file: NetLbfo_Cmdlets.xml
Module Name: NetLbfo
online version: https://learn.microsoft.com/powershell/module/netlbfo/add-netlbfoteamnic?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-NetLbfoTeamNic

## SYNOPSIS
Adds a new interface to a NIC team.

## SYNTAX

```
Add-NetLbfoTeamNic [-Team] <String> [-VlanID] <UInt32> [[-Name] <String>] [-AsJob] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Add-NetLbfoTeamNic** cmdlet adds a new team interface to the specified NIC team.
You can use this cmdlet to add the interfaces to the specified team by specifying the respective VLAN IDs.

You need administrator privileges to use **Add-NetLbfoTeamNic**.

## EXAMPLES

### Example 1: Add a team interface
```
PS C:\>Add-NetLbfoTeamNIC -Team Team1 -VlanID 42
```

This command adds a team interface with VLAN ID 42 to the specified team named Team1.

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
Specifies the name of the new team interface.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ifAlias, InterfaceAlias

Required: False
Position: 3
Default value: <TeamName> -VLAN <VlanID>
Accept pipeline input: False
Accept wildcard characters: False
```

### -Team
Specifies the name of the NIC team to which to add a new team interface.

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

### -VlanID
Specifies the VLAN ID of the team interface.
VlanID values must meet the criteria 0 ≤ VlanID \< 4095.
Specify the value 0 to match frames identified with a VLAN ID of 0 or untagged frames.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None
This cmdlet takes no input objects.

## OUTPUTS

### MSFT_NetLbfoTeamNic
This cmdlet produces an **MFT_NetLbfoTeamNic** object containing the newly created team interface.

## NOTES

## RELATED LINKS

[Get-NetLbfoTeamNic](./Get-NetLbfoTeamNic.md)

[Remove-NetLbfoTeamNic](./Remove-NetLbfoTeamNic.md)

[Set-NetLbfoTeamNic](./Set-NetLbfoTeamNic.md)

