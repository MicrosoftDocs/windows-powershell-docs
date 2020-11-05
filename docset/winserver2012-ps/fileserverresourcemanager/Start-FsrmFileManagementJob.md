---
external help file: FSRM_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 957E5451-80A7-4647-BA2D-2662E83B8AAE
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Start-FsrmFileManagementJob

## SYNOPSIS
Starts a file management job.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Start-FsrmFileManagementJob [-Name] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-Queue]
 [-RunDuration <Int32>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Start-FsrmFileManagementJob [-AsJob] [-CimSession <CimSession[]>] [-Queue] [-RunDuration <Int32>]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Start-FsrmFileManagementJob** cmdlet attempts to start a file management job.
If you specify the **Queue** parameter, the start is delayed by approximately 5 minutes to wait for other file management jobs that the server can run at the same time.

## EXAMPLES

### Example 1: Start a file management job
```
PS C:\>Start-FsrmFileManagementJob -Name "Expire stale Data"
```

This command starts the file management job named "Expire stale Data" immediately.

### Example 2: Queue a file management job and set the run duration
```
PS C:\>Start-FsrmFileManagementJob -Name "Expire stale Data" -Queue -RunDuration 4
```

This command queues the file management job named "Expire stale Data" to start in the next 5 minutes and specifies that the server does not run the job any longer than 4 hours.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array of names of file management jobs.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Queue
Indicates that the server adds the file management job to a queue and the task should run the next 5 minutes.
Any tasks that the server queues during the next 5 minutes are run together.
If you do not specify this parameter, the server runs the file management job immediately.

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

### -RunDuration
Specifies the number of hours that the server runs the task before canceling it.
The value 0 indicates that the server runs the task to completion.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMFileManagementJob

## NOTES

## RELATED LINKS

[Get-FsrmFileManagementJob](./Get-FsrmFileManagementJob.md)

[Set-FsrmFileManagementJob](./Set-FsrmFileManagementJob.md)

[New-FsrmFileManagementJob](./New-FsrmFileManagementJob.md)

[Remove-FsrmFileManagementJob](./Remove-FsrmFileManagementJob.md)

[Stop-FsrmFileManagementJob](./Stop-FsrmFileManagementJob.md)

[Wait-FsrmFileManagementJob](./Wait-FsrmFileManagementJob.md)

