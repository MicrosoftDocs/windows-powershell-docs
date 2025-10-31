---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FsrmQuota.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/new-fsrmquota?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-FsrmQuota
---

# New-FsrmQuota

## SYNOPSIS
Creates a FSRM quota.

## SYNTAX

```
New-FsrmQuota [-Path] <String> [-Description <String>] [-Template <String>] [-Size <UInt64>] [-Disabled]
 [-SoftLimit] [-Threshold <CimInstance[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-FsrmQuota** cmdlet creates a File Server Resource Manager (FSRM) quota on the server.
The quota applies to the directory and all its subdirectories (recursively).
Quotas that you specify on folders higher in the hierarchy further restrict the quota specified on a folder.

## EXAMPLES

### Example 1: Create a hard limit quota
```
PS C:\> New-FsrmQuota -Path "C:\Shares" -Description "limit usage to 1 GB." -Size 1GB
```

This command creates a quota on C:\Shares and adds a description for the quota.
The quota is configured as a hard limit at 1GB in size that does not have any thresholds.
A hard limit quota prevents users from saving files after the space limit is reached and generates notifications when the volume of data reaches each configured threshold.

### Example 2: Create a quota based on a quota template
```
PS C:\> New-FsrmQuota -Path "C:\Shares" -Description "limit usage to 100 MB based on template." -Template "100 MB Limit"
```

This command creates a quota on C:\Shares based on the template named 100 MB Limit.
The command specifies a description for the quota that is different from the description in the template.
The quota is configured as a hard limit at 100 MB in size that does not have any thresholds.

### Example 3: Create a soft limit quota that runs a command
```
The first command creates an FSRM action object and stores the results in the $Action variable. The action indicates that when an associated event occurs, the server run Cmd.exe with the specified parameters. The command specifies that server record errors codes from the executed command in the error log.
PS C:\> $Action = New-FsrmAction -Type Command -Command "c:\windows\system32\cmd.exe" -CommandParameters "echo [source file path] >> c:\log.txt" -ShouldLogError

The second command creates a threshold object and stores the results in the $Threshold variable. The command specifies the percentage of the quota limit at which to execute the action, and specifies the action stored in the $Action variable.
PS C:\> $Threshold = New-FsrmQuotaThreshold -Percentage 90 -Action $action

The third command creates a quota on C:\Shares and specifies the threshold stored in the $Threshold variable. The *SoftLimit* parameter indicates the quota reports on the disk usage with respect to the size limit and run thresholds, but does not enforce the size limit.
PS C:\> New-FsrmQuota -Path "C:\Shares" -Size 128MB -Threshold $Threshold -SoftLimit
```

This example creates a new quota on C:\Shares that has a soft limit at 128MB, a threshold at 90% usage, and that runs a custom command.

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

### -Disabled
Indicates that the quota is disabled.

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

### -Path
Specifies a valid local path to a folder.

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
Specifies the space limit that the quota template enforces.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
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

### -Template
Specifies the name of a quota template on the server.

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
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-FsrmQuota](./Get-FsrmQuota.md)

[Remove-FsrmQuota](./Remove-FsrmQuota.md)

[Reset-FsrmQuota](./Reset-FsrmQuota.md)

[Set-FsrmQuota](./Set-FsrmQuota.md)

[Update-FsrmQuota](./Update-FsrmQuota.md)

