---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_MpPreference.cdxml-help.xml
Module Name: Defender
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/defender/get-mppreference?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-MpPreference
---

# Get-MpPreference

## SYNOPSIS
Gets preferences for the Windows Defender scans and updates.

## SYNTAX

```
Get-MpPreference
 [-AsJob]
 [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Get-MpPreference` cmdlet gets preferences for the Windows Defender scans and updates. For more
information about the preferences that this cmdlet retrieves, see
[Windows Defender Preferences Class](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)).

## EXAMPLES

### Example 1: View the scheduled scan day

```powershell
PS C:\> $Preferences = Get-MpPreference
PS C:\> $Preferences.ScanScheduleDay
```

The first command gets the preferences, and then stores them in the **$Preferences** variable.

The second command uses standard dot syntax to display the **ScanScheduleDay** property of the
object stored in the **$Preferences** variable.

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

The cmdlet immediately returns an object that represents the job and then displays the command
prompt. You can continue to work in the session while the job completes. To manage the job, use the
`*-Job` cmdlets. To get the job results, use the
[Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see
[about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967)
or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. The default is the
current session on the local computer.

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

### -ThrottleLimit

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-MpPreference](./Add-MpPreference.md)

[Remove-MpPreference](./Remove-MpPreference.md)

[Set-MpPreference](./Set-MpPreference.md)
