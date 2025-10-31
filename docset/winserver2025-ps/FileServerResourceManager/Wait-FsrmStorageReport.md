---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FsrmStorageReport.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/wait-fsrmstoragereport?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-FsrmStorageReport
---

# Wait-FsrmStorageReport

## SYNOPSIS
Waits for a period of time or until storage reports is finished running.

## SYNTAX

### Query (cdxml) (Default)
```
Wait-FsrmStorageReport [-Name] <String[]> [-Timeout <Int32>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Wait-FsrmStorageReport -InputObject <CimInstance[]> [-Timeout <Int32>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Wait-FsrmStorageReport** cmdlet waits for a period of time or until one or more storage reports are finished running.
The cmdlet returns when the server finishes running the storage reports or when the time that you specify in the *Timeout* parameter has elapsed.

## EXAMPLES

### Example 1: Wait for a storage report
```
PS C:\> Start-FsrmStorageReport -Name "Monthly report"
PS C:\> Wait-FsrmStorageReport -Name "Monthly report"
```

The first command starts the report named "Monthly report".

The second command waits for the report to finish running.

### Example 2: Wait for and stop the storage report
```
The first command starts the report named "Monthly report".
PS C:\> Start-FsrmStorageReport -Name "Monthly report"

The second command waits for the report to finish running. If the report is not completed in 10 minutes, the server ends the report job and the cmdlet returns.
PS C:\> Wait-FsrmStorageReport -Name "Monthly report" -Timeout 600

The third command ensures that the report has stopped running.
PS C:\> Stop- FsrmStorageReport -Name "Monthly report"
```

This example waits for the report to finish running and then stops the report.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

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
Specifies an array of names of storage reports.

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
Aliases:

Required: True
Position: 1
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

### -Timeout
Specifies the number of seconds to wait for reports to complete.
The cmdlet returns when the period expires or the report completes.
To wait indefinitely, set the value to -1.
The value must be in the range from -1 through 2,147,483.

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

### System.String[]

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS

[Get-FsrmStorageReport](./Get-FsrmStorageReport.md)

[New-FsrmStorageReport](./New-FsrmStorageReport.md)

[Remove-FsrmStorageReport](./Remove-FsrmStorageReport.md)

[Set-FsrmStorageReport](./Set-FsrmStorageReport.md)

[Start-FsrmStorageReport](./Start-FsrmStorageReport.md)

[Stop-FsrmStorageReport](./Stop-FsrmStorageReport.md)

