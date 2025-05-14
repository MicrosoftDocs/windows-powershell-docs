---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FsrmQuotaTemplate.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/new-fsrmquotatemplate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-FsrmQuotaTemplate
---

# New-FsrmQuotaTemplate

## SYNOPSIS
Creates a quota template.

## SYNTAX

```
New-FsrmQuotaTemplate [-Name] <String> [-Description <String>] -Size <UInt64> [-SoftLimit]
 [-Threshold <CimInstance[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-FsrmQuotaTemplate** cmdlet creates a quota template.
A quota template defines a space limit, the type of quota (hard or soft), and (optionally) a set of notifications that the server generates automatically when quota usage reaches the threshold levels that you define.

## EXAMPLES

### Example 1: Create a hard limit quota template
```
PS C:\> New-FsrmQuotaTemplate -Name "1GB limit" -Description "limit usage to 1 GB." -Size 1GB
```

This command creates a quota template named "1GB limit".
The command adds a description for the quota template and configures a hard size limit at 1GB that does not have any thresholds.
A hard limit quota prevents users from saving files after the space limit is reached and generates notifications when the volume of data reaches each threshold.

### Example 2: Create a soft limit quota template that runs a command
```
The first command creates an FSRM action object and stores the results in the $Action variable. The action indicates that when an associated event occurs, the server run Cmd.exe with the specified parameters. The command specifies that server record errors codes from the executed command in the error log.
PS C:\> $Action = New-FsrmAction -Type Command -Command "c:\windows\system32\cmd.exe" -CommandParameters "echo [source file path] >> c:\log.txt" -ShouldLogError

The second command creates a threshold object and stores the results in the $Threshold variable. The command specifies the percentage of the quota limit at which to execute the action, and specifies the action stored in the $Action variable.
PS C:\> $Threshold = New-FsrmQuotaThreshold -Percentage 90 -Action $action

The third command creates a quota template named "128MB limit" and specifies the threshold stored in the $Threshold variable. The *SoftLimit* parameter indicates the quota reports on the disk usage with respect to the size limit and run thresholds, but does not enforce the size limit.
PS C:\> New-FsrmQuotaTemplate -Name "128MB limit" -Size 128MB -Threshold $Threshold -SoftLimit
```

This example creates a quota template that has a soft limit at 128MB, a threshold at 90% usage, and that runs a custom command.

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

### -Description
Specifies a description for the quota.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the quota.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Size
Specifies the size limit that the quota enforces.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SoftLimit
Indicates that the quota reports on the disk usage with respect to the size limit and run thresholds, but does not enforce the size limit.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Threshold
Specifies an array of threshold objects.

The threshold object defines a percentage of used space from the available space that can be reached during a file operation, and a set of actions that the server takes when a quota reaches the threshold.
To perform the action when the quota is exceeded, set the threshold to 100 (percent).
You can use the **New-FsrmQuotaThreshold** cmdlet to create a threshold object.

```yaml
Type: CimInstance[]
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

### System.String

### System.UInt64

### System.Management.Automation.SwitchParameter

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-FsrmQuotaTemplate](./Get-FsrmQuotaTemplate.md)

[Remove-FsrmQuotaTemplate](./Remove-FsrmQuotaTemplate.md)

[Set-FsrmQuotaTemplate](./Set-FsrmQuotaTemplate.md)

