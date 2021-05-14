---
external help file: FSRM_Cmdlets.xml
Module Name: FileServerResourceManager
online version: https://docs.microsoft.com/powershell/module/fileserverresourcemanager/start-fsrmclassification?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Start-FsrmClassification

## SYNOPSIS
Starts the classification process.

## SYNTAX

```
Start-FsrmClassification [-AsJob] [-CimSession <CimSession[]>] [-Queue] [-RunDuration <Int32>]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Start-FsrmClassification** cmdlet starts the classification process.
The classification process runs classification rules on files on the server and generates the classification report.

## EXAMPLES

### Example 1: Start the classification process
```
PS C:\>Start-FsrmClassification -RunDuration 4
```

This command starts the classification process and specifies that the server runs the classification task no longer than 4 hours before canceling it.

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

### -Queue
Indicates that the server adds the classification task to a queue and the task should run in the next 5 minutes.
Any tasks that the server queues during the next 5 minutes run together.
If you do not specify this parameter, the server runs the classification immediately.

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

### -RunDuration
Specifies the number of hours that the server runs the classification task before canceling it.
The value 0 indicates that the server runs the task to completion.

```yaml
Type: Int32
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMClassification

## NOTES

## RELATED LINKS

[Get-FsrmClassification](./Get-FsrmClassification.md)

[Stop-FsrmClassification](./Stop-FsrmClassification.md)

[New-FsrmClassificationRule](./New-FsrmClassificationRule.md)

[Set-FsrmClassification](./Set-FsrmClassification.md)

[Wait-FsrmClassification](./Wait-FsrmClassification.md)

