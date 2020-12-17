---
external help file: FSRM_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: C524CA07-0DE5-41D8-B958-A05C6B27F9C8
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Start-FsrmStorageReport

## SYNOPSIS
Starts generating storage reports.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Start-FsrmStorageReport [-Name] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-Queue]
 [-RunDuration <Int32>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Start-FsrmStorageReport [-AsJob] [-CimSession <CimSession[]>] [-Queue] [-RunDuration <Int32>]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Start-FsrmStorageReport** cmdlet starts generating one or more storage reports on demand.
You cannot use this cmdlet to start interactive storage reports or storage reports that do not have a schedule.

You can view the reports immediately after the server generates them or e-mail the reports to a group of administrators.
If you choose to open the reports immediately, you must wait while the reports are generated.
Processing time varies, depending on the types of reports and the scope of the data.

## EXAMPLES

### Example 1: Start a storage report
```
PS C:\>Start-FsrmStorageReport "Monthly report"
```

This command starts the storage report named "Monthly report" immediately.

### Example 2: Queue a storage report and set the run duration
```
PS C:\>Start-FsrmStorageReport "Monthly report" -Queue -RunDuration 4
```

This command queues the storage report named "Monthly report" to start in the next 5 minutes and specifies that the server does not run the report job any longer than 4 hours.

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
Specifies an array of names of storage reports.

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
Indicates that the server adds the report to a queue and the report should run in the next 5 minutes.
Any reports that the server queues during the next 5 minutes are run together.
If you do not specify this parameter, the server runs the report immediately.

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
Specifies the number of hours that the server runs the report job before canceling it.
The value 0 indicates that the server runs the report job to completion.

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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMStorageReport

## NOTES

## RELATED LINKS

[Get-FsrmStorageReport](./Get-FsrmStorageReport.md)

[Set-FsrmStorageReport](./Set-FsrmStorageReport.md)

[New-FsrmStorageReport](./New-FsrmStorageReport.md)

[Stop-FsrmStorageReport](./Stop-FsrmStorageReport.md)

[Wait-FsrmStorageReport](./Wait-FsrmStorageReport.md)

[Remove-FsrmStorageReport](./Remove-FsrmStorageReport.md)

