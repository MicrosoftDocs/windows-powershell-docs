---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetLbfoTeamNic.cdxml-help.xml
Module Name: NetLbfo
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netlbfo/set-netlbfoteamnic?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetLbfoTeamNic
---

# Set-NetLbfoTeamNic

## SYNOPSIS
Sets a new VLAN id on a team interface, or restores the interface to Default mode.

## SYNTAX

### ByNameOrTeam (Default)
```
Set-NetLbfoTeamNic [[-Name] <String[]>] [[-Team] <String[]>] [-VlanID <UInt32>] [-Default]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByTeamOfTheTeamNic
```
Set-NetLbfoTeamNic [-TeamOfTheTeamNic <CimInstance>] [-VlanID <UInt32>] [-Default] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetLbfoTeamNic -InputObject <CimInstance[]> [-VlanID <UInt32>] [-Default] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetLbfoTeamNic** cmdlet sets the optional values on a team interface.
Only the team interface that was created when the team was created can be set to Default mode.

You must have administrator rights to run **Set-NetLbfoTeamNic**.

## EXAMPLES

### Example 1: Set the VLAN ID
```
PS C:\>Set-NetLbfoTeamNIC -Name "Team1 - VlanID 42" -VlanID 15
```

This command modifies the current VLAN ID of the team interface named "Team1 - VLAN 42" to the VLAN ID 15.

### Example 2: Set the VLAN ID of the primary interface to 5, and then revert it to default
```
PS C:\> Set-NetLbfoTeamNic -Name "Team1" -VlanID 5

This command changes the primary team interface Team1 - VLAN 5 to default mode.
PS C:\> Set-NetLbfoTeamNic -Name "Team1 - VLAN 5" -Default
```

This command sets the VLAN ID of the primary team interface named Team1 to 5.

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

### -Default
Indicates that the team interface should be restored to Default mode.

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

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the team interface to modify.

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

### -Team
Specifies the name of the NIC team for which to modify the team interface.

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
Specifies the network adapter team object whose team interfaces are to be modified.

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

### -VlanID
Specifies the VLAN ID of the team interface to modify.

```yaml
Type: UInt32
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet takes no input objects.

## OUTPUTS

### None
By default, this cmdlet produces no output.

If the *PassThru* parameter is specified, the cmdlet returns the newly modified **MSFT_NetLbfoTeamNic** object.

## NOTES

## RELATED LINKS

[Add-NetLbfoTeamNic](./Add-NetLbfoTeamNic.md)

[Get-NetLbfoTeamNic](./Get-NetLbfoTeamNic.md)

[Remove-NetLbfoTeamNic](./Remove-NetLbfoTeamNic.md)

