---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterCollection.cdxml-help.xml
Module Name: FailoverClusters
ms.date: 10/21/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/set-clustergroupset?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ClusterGroupSet
---

# Set-ClusterGroupSet

## SYNOPSIS
Updates a cluster group set.

## SYNTAX

### Query (cdxml) (Default)

```
Set-ClusterGroupSet [[-Name] <String[]>] [-StartupSetting <StartupSettingType>]
 [-StartupCount <UInt32>] [-IsGlobal <Boolean>] [-StartupDelay <UInt32>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)

```
Set-ClusterGroupSet -InputObject <CimInstance[]> [-StartupSetting <StartupSettingType>]
 [-StartupCount <UInt32>] [-IsGlobal <Boolean>] [-StartupDelay <UInt32>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

The `Set-ClusterGroupSet` cmdlet updates a cluster group set. To update the groups in the set, use
the `Add-ClusterGroupToSet` and `Remove-ClusterGroupFromSet` cmdlets. To update the dependencies,
use the `Add-ClusterGroupSetDependency` and `Remove-ClusterGroupSetDependency` cmdlets.

## EXAMPLES

### Example 1: Change a group set to the specified startup setting

```powershell
Set-ClusterGroupSet -Name "Set002" -StartupDelayTrigger Online
```

This command changes the group set named `Set002` to the startup setting Online.

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

### -IsGlobal

Indicates that this cmdlet sets the group set as global.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Specifies the name of the group set.

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Returns an object representing the item with which you are working. By default, this cmdlet doesn't
generate any output.

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

### -StartupCount

Specifies the number of groups to meet the ready setting.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: Count

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartupDelay

Specifies the delay to use after reaching the ready state, in seconds.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: Delay

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartupSetting

Specifies the startup setting when the set is deemed ready. When delay it is when the groups
specified in the **StartupCount** parameter are in pending in addition to the **StartupDelay**
parameter. If it is online it is when **StartupCount** groups reach online in addition to the delay.

The acceptable values for this parameter are: `Delay` or `Online`.

```yaml
Type: StartupSettingType
Parameter Sets: (All)
Aliases: StartupDelayTrigger
Accepted values: Delay, Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an
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

[Get-ClusterGroupSet](./Get-ClusterGroupSet.md)

[New-ClusterGroupSet](./New-ClusterGroupSet.md)

[Remove-ClusterGroupSet](./Remove-ClusterGroupSet.md)
