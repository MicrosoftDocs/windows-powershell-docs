---
description: The Add-MpPreference cmdlet modifies settings for Windows Defender.
external help file: MSFT_MpPreference.cdxml-help.xml
Module Name: Defender
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/defender/add-mppreference?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-MpPreference
---

# Add-MpPreference

## SYNOPSIS
Modifies settings for Windows Defender.

## SYNTAX

```
Add-MpPreference
 [-AsJob]
 [-AttackSurfaceReductionOnlyExclusions <String[]>]
 [-AttackSurfaceReductionRules_Actions <ASRRuleActionType[]>]
 [-AttackSurfaceReductionRules_Ids <String[]>]
 [-CimSession <CimSession[]>]
 [-ControlledFolderAccessAllowedApplications <String[]>]
 [-ControlledFolderAccessProtectedFolders <String[]>]
 [-ExclusionExtension <String[]>]
 [-ExclusionIpAddress <String[]>]
 [-ExclusionPath <String[]>]
 [-ExclusionProcess <String[]>]
 [-Force]
 [-ThreatIDDefaultAction_Actions <ThreatAction[]>]
 [-ThreatIDDefaultAction_Ids <Int64[]>]
 [-ThrottleLimit <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Add-MpPreference` cmdlet modifies settings for Windows Defender. Use this cmdlet to add
exclusions for file name extensions, paths, and processes, and to add default actions for high,
moderate, and low threats.

## EXAMPLES

### Example 1: Add a folder to the exclusion list

```powershell
Add-MpPreference -ExclusionPath 'C:\Temp'
```

This command adds the folder C:\Temp to the exclusion list.
The command disables Windows Defender scheduled and real-time scanning for files in this folder.

### Example 2: Allow an application to access folders

```powershell
Add-MpPreference -ControlledFolderAccessAllowedApplications 'c:\apps\test.exe'
```

This command allows the specified application to make changes in controlled folders.

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

### -AttackSurfaceReductionOnlyExclusions

Specifies the files and paths to exclude from attack surface reduction (ASR) rules. Specifies the
folders or files and resources that should be excluded from ASR rules. Enter a folder path or a
fully qualified resource name. For example, `C:\Windows` excludes all files in that directory.
`C:\Windows\App.exe` excludes only that specific file in that specific folder.

See the
[ASR rules](/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules)
topic for more information about excluding files and folders from ASR rules.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AttackSurfaceReductionRules_Actions

Specifies the states of attack surface reduction rules specified by using the
**AttackSurfaceReductionRules_Ids** parameter. If you add multiple rules as a comma-separated list,
specify their states separately as a comma-separated list.

```yaml
Type: ASRRuleActionType[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AttackSurfaceReductionRules_Ids

Specifies the IDs of attack surface reduction rules. Use the **AttackSurfaceReductionRules_Actions**
parameter to specify the state for each rule. If you add multiple rules as a comma-separated list,
specify their states separately as a comma-separated list.

```yaml
Type: String[]
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

### -ControlledFolderAccessAllowedApplications

Specifies applications that can make changes in controlled folders.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControlledFolderAccessProtectedFolders

Specifies more folders to protect.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExclusionExtension

Specifies an array of file name extensions, such as `obj` or `lib`, to exclude from scheduled, custom,
and real-time scanning. This cmdlet adds these file name extensions to the exclusions.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExclusionIpAddress

Specifies an array of IP addresses to exclude from scheduled and real-time scanning.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExclusionPath

Specifies an array of file paths to exclude from scheduled and real-time scanning.
You can specify a folder to exclude all the files under the folder.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExclusionProcess

Specifies an array of processes, as paths to process images. This cmdlet excludes any files opened
by the processes that you specify from scheduled and real-time scanning. Specifying this parameter
excludes files opened by executable programs only. The cmdlet does not exclude the processes
themselves. To exclude a process, specify it by using the **ExclusionPath** parameter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Forces the command to run without asking for user confirmation.

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

### -ThreatIDDefaultAction_Actions

Specifies an array of the actions to take for the IDs specified by using the
**ThreatIDDefaultAction_Ids** parameter. The acceptable values for this parameter are:

- `1`: Clean
- `2`: Quarantine
- `3`: Remove
- `6`: Allow
- `8`: UserDefined
- `9`: NoAction
- `10`: Block

```yaml
Type: ThreatAction[]
Parameter Sets: (All)
Aliases: tiddefaca
Accepted values: Clean, Quarantine, Remove, Allow, UserDefined, NoAction, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThreatIDDefaultAction_Ids

Specifies an array of threat IDs.
This cmdlet adds the default action for the threat IDs that you specify.

```yaml
Type: Int64[]
Parameter Sets: (All)
Aliases: tiddefaci

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

[Get-MpPreference](./Get-MpPreference.md)

[Remove-MpPreference](./Remove-MpPreference.md)

[Set-MpPreference](./Set-MpPreference.md)
