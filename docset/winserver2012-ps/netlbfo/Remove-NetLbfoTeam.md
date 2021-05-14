---
external help file: NetLbfo_Cmdlets.xml
Module Name: NetLbfo
online version: https://docs.microsoft.com/powershell/module/netlbfo/remove-netlbfoteam?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-NetLbfoTeam

## SYNOPSIS
Removes the specified NIC team from the host.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-NetLbfoTeam [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-NetLbfoTeam [-Name] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-NetLbfoTeam** cmdlet removes the specified NIC team from the host.
This cmdlet disconnects all associated team members and providers from the team.
You can specify the team to remove by using either a team object retrieved by Get-NetLbfoTeam, or by specifying a team name.

You can use **Remove-NetLbfoTeam** to remove all NIC teams from the server.

You need administrator privileges to use **Remove-NetLbfoTeam**.

## EXAMPLES

### Example 1: Remove a team
```
PS C:\>Remove-NetLbfoTeam -Name Team1
```

This command removes the team named Team1.

### Example 2: Remove a team using a team object
```
PS C:\>$team = Get-NetLbfoTeam -Name Team1



PS C:\>Remove-NetLbfoTeam -InputObject $team
```

This set of commands retrieves a team object into a variable $team using Get-NetLbfoTeam, and then passes the variable to **Remove-NetLbfoTeam**.

### Example 3: Remove all teams from the server
```
PS C:\>Get-NetLbfoTeam | Remove-NetLbfoTeam
```

This command retrieves all the teams from the server using Get-NetLbfoTeam cmdlet and then sends all the retrieved teams to **Remove-NetLbfoTeam** which removes the teams.

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

### -InputObject
Specifies the team object which contains the NIC team to remove.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the NIC team to remove.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None
This cmdlet takes no input objects.

## OUTPUTS

### None
By default, this cmdlet produces no output.

## NOTES

## RELATED LINKS

[New-NetLbfoTeam](./New-NetLbfoTeam.md)

[Get-NetLbfoTeam](./Get-NetLbfoTeam.md)

[Set-NetLbfoTeam](./Set-NetLbfoTeam.md)

[Rename-NetLbfoTeam](./Rename-NetLbfoTeam.md)

