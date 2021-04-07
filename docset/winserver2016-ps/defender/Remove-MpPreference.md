---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_MpPreference.cdxml-help.xml
manager: jasgro
Module Name: Defender
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/defender/remove-mppreference?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-MpPreference
---

# Remove-MpPreference

## SYNOPSIS
Removes exclusions or default actions.

## SYNTAX

```
Remove-MpPreference [-ExclusionPath <String[]>] [-ExclusionExtension <String[]>] [-ExclusionProcess <String[]>]
 [-ThreatIDDefaultAction_Ids <Int64[]>] [-UnknownThreatDefaultAction] [-LowThreatDefaultAction]
 [-AttackSurfaceReductionOnlyExclusions <String>]
 [-ModerateThreatDefaultAction] [-HighThreatDefaultAction] [-SevereThreatDefaultAction] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-MpPreference** cmdlet removes exclusions for file name extensions, paths, and processes, or default actions for high, moderate, and low threats.
If you attempt to remove an exclusion that is not in the list, this cmdlet reports the error.

## EXAMPLES

### Example 1: Remove a folder from the exclusion list
```
PS C:\> Remove-MpPreference -ExclusionPath "C:\Temp"
```

This command removes the folder C:\Temp from the exclusion list.

### Example 2: 
```
PS C:\> Remove-MpPreference -AttackSurfaceReductionOnlyExclusions "C:\Windows\App.exe"
```

This command will exclude only that specific file app.exe in that specific folder.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete. 

The cmdlet immediately returns an object that represents the job and then displays the command prompt. 
You can continue to work in the session while the job completes. 
To manage the job, use the `*-Job` cmdlets. 
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet. 

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Exclude files and paths from Attack Surface Reduction (ASR) rules. Specify the folders or files and resources that should be excluded from ASR rules. Enter a folder path or a fully qualified resource name. For example, ""C:\Windows"" will exclude all files in that directory. ""C:\Windows\App.exe"" will exclude only that specific file in that specific folder.

For more information about excluding files and folders from [ASR rules](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules).

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

### -ExclusionExtension
Specifies an array of file name extensions, such as obj or lib, to exclude from scheduled, custom, and real-time scanning.
This cmdlet removes the exclusions that you specify.

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
This cmdlet removes the exclusions that you specify.

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
Specifies an array of processes, as paths to process images.
This cmdlet removes exclusions of files opened by the processes that you specify.

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

### -HighThreatDefaultAction
Indicates that this cmdlet removes the automatic remediation action specified for the high threat alert level.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: htdefac

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LowThreatDefaultAction
Indicates that this cmdlet removes the automatic remediation action specified for the low threat alert level.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ltdefac

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModerateThreatDefaultAction
Indicates that this cmdlet removes the automatic remediation action specified for the moderate threat alert level.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: mtdefac

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SevereThreatDefaultAction
Indicates that this cmdlet removes the automatic remediation action specified for the severe threat alert level.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: stdefac

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThreatIDDefaultAction_Ids
Specifies an array of threat IDs.
This cmdlet removes the default actions for the threat IDs that you specify.

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

### -UnknownThreatDefaultAction
Indicates that this cmdlet removes the automatic remediation action specified for the unknown threat alert level.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: unktdefac

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-MpPreference](./Add-MpPreference.md)

[Get-MpPreference](./Get-MpPreference.md)

[Set-MpPreference](./Set-MpPreference.md)
