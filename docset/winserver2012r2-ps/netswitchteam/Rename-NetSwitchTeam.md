---
external help file: MSFT_NetSwitchTeam.cdxml-help.xml
Module Name: NetSwitchTeam
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/netswitchteam/rename-netswitchteam?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-NetSwitchTeam
---

# Rename-NetSwitchTeam

## SYNOPSIS
Changes the name of a switch team.

## SYNTAX

```
Rename-NetSwitchTeam [-Name] <String> [-NewName] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Rename-NetSwitchTeam** cmdlet changes the name of a switch team.
Only the name of a switch team can be changed using this cmdlet.

The current switch team name may contain wildcard characters, as long as the wildcard mask resolves to a single switch team.

The new switch team name must not match an existing switch team name.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Rename-NetSwitchTeam -Name "MyTeam1" -NewName "SwitchTeam1"
```

This example renames the switch team named MyTeam1 to the new name SwitchTeam1.

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
Specifies the current name of switch team to rename.
Wildcard characters may be used to specify the current switch team name, as long as the wildcard mask resolves to a single switch team.
The wildcard mask must not resolve to one than one switch team name.

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

### -NewName
Specifies the new name to give to the switch team.
The new name must not already exist.
The new name cannot be an existing switch team or Load-Balancing/Fail-Over (LBFO) team name.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NetSwitchTeam](./Get-NetSwitchTeam.md)

[New-NetSwitchTeam](./New-NetSwitchTeam.md)

[Remove-NetSwitchTeam](./Remove-NetSwitchTeam.md)

