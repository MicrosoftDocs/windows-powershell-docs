---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetLbfoTeam.cdxml-help.xml
Module Name: NetLbfo
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netlbfo/rename-netlbfoteam?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-NetLbfoTeam
---

# Rename-NetLbfoTeam

## SYNOPSIS
Renames a NIC team.

## SYNTAX

```
Rename-NetLbfoTeam [-Name] <String> [-NewName] <String> [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Rename-NetLbfoTeam** cmdlet renames the specified NIC team to the specified new name.
Also updates the team interface names accordingly, if they use default values.

You must have administrator rights to run **Rename-NetLbfoTeam**.

## EXAMPLES

### Example 1: Rename a team
```
PS C:\> Rename -NetLbfoTeam -Name "Team1" -NewName "TeamA"
```

This command renames the team named Team1 to TeamA.

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
Specifies the name of the NIC team to rename.

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
Specifies the new name of the NIC team.

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

### MSFT_NetLbfoTeam
If the *PassThru* parameter is specified, this cmdlet produces newly renamed team object.
If the *PassThru* parameter is not specified, there is no output.

## NOTES

## RELATED LINKS

[Get-NetLbfoTeam](./Get-NetLbfoTeam.md)

[New-NetLbfoTeam](./New-NetLbfoTeam.md)

[Remove-NetLbfoTeam](./Remove-NetLbfoTeam.md)

[Set-NetLbfoTeam](./Set-NetLbfoTeam.md)

