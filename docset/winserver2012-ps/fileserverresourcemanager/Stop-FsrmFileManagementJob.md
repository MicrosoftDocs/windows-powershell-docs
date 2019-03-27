---
external help file: FSRM_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: C4D3D777-7C98-4B3D-942C-088A7F11F5BD
manager: dansimp
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Stop-FsrmFileManagementJob

## SYNOPSIS
Stops the running instance of a file management job.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Stop-FsrmFileManagementJob [-Name] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Stop-FsrmFileManagementJob [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Stop-FsrmFileManagementJob** cmdlet stops the running instance of a file management job.
This cmdlet returns one of the following values for the running status of the file management job: 
- NotRunning
- Queued
- Running

This cmdlet returns a success status in the following conditions: 
- The server is not running the job. 
- The server is currently canceling the job. 
- The server is running the job and has started cancellation of the job. 
- The job is queued on the server and has removed the job from the queue.

This cmdlet returns a failure status if the server cannot stop a file management job that is running or is queued.

## EXAMPLES

### Example 1: Stop a file management job
```
PS C:\>Start-FsrmFileManagementJob -Name "Expire stale data" PS C:\>Stop-FsrmFileManagementJob -Name "Expire stale data"
```

This first command starts the file management job named "Expire stale data".

This second command stops the file management job named "Expire stale data".

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

## NOTES

## RELATED LINKS

[Get-FsrmFileManagementJob](./Get-FsrmFileManagementJob.md)

[Set-FsrmFileManagementJob](./Set-FsrmFileManagementJob.md)

[New-FsrmFileManagementJob](./New-FsrmFileManagementJob.md)

[Remove-FsrmFileManagementJob](./Remove-FsrmFileManagementJob.md)

[Start-FsrmFileManagementJob](./Start-FsrmFileManagementJob.md)

[Wait-FsrmFileManagementJob](./Wait-FsrmFileManagementJob.md)

