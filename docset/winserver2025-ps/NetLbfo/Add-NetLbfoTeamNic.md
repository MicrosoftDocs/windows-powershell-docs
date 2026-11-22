---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetLbfoTeamNic.cdxml-help.xml
Module Name: NetLbfo
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netlbfo/add-netlbfoteamnic?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-NetLbfoTeamNic
---

# Add-NetLbfoTeamNic

## SYNOPSIS
Adds a new interface to a NIC team.

## SYNTAX

```
Add-NetLbfoTeamNic [-Team] <String> [-VlanID] <UInt32> [[-Name] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-NetLbfoTeamNic** cmdlet adds a new team interface to the specified NIC team.
You can use this cmdlet to add the interfaces to the specified team by specifying the respective VLAN IDs.

You must have administrator rights to use **Add-NetLbfoTeamNic**.

## EXAMPLES

### Example 1: Add a team interface
```
PS C:\> Add-NetLbfoTeamNIC -Team "Team1" -VlanID 42
```

This command adds a team interface with VLAN ID 42 to the specified team named Team1.

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

### -Name
Specifies the name of the new team interface.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ifAlias, InterfaceAlias

Required: False
Position: 2
Default value: None
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
Position: 0
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
Position: 1
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

### MSFT_NetLbfoTeamNic
This cmdlet produces an **MFT_NetLbfoTeamNic** object containing the newly created team interface.

## NOTES

## RELATED LINKS

[Get-NetLbfoTeamNic](./Get-NetLbfoTeamNic.md)

[Remove-NetLbfoTeamNic](./Remove-NetLbfoTeamNic.md)

[Set-NetLbfoTeamNic](./Set-NetLbfoTeamNic.md)

