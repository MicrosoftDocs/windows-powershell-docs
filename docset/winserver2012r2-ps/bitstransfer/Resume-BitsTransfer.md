---
external help file: Microsoft.BackgroundIntelligentTransfer.Management.dll-Help.xml
Module Name: BitsTransfer
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/bitstransfer/resume-bitstransfer?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-BitsTransfer
---

# Resume-BitsTransfer

## SYNOPSIS
Resumes a Background Intelligent Transfer Service (BITS) transfer job.

## SYNTAX

```
Resume-BitsTransfer [-BitsJob] <BitsJob[]> [-Asynchronous] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Resume-BitsTransfer** cmdlet resumes one or more suspended BITS transfer jobs.
If the BITS transfer is already in process, the cmdlet does nothing.
You can view the current state of a transfer job by using the **Get-BitsTransfer** cmdlet.

Important: By default, the **Resume-BitsTransfer** cmdlet restarts the transfer job synchronously even if the original job was specified as an asynchronous transfer job.
You could use this behavior to convert an asynchronous transfer job into a synchronous transfer job.
You could do this if either of the following conditions is true:

- The asynchronous transfer job was created outside cmdlets.

- The asynchronous transfer job was created by using the **Start-BitsTransfer** cmdlet.

If you want to restart the transfer job as an asynchronous transfer, use the **Asynchronous** parameter.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-BitsTransfer | Resume-BitsTransfer
```

This command resumes all the BITS transfer jobs that are owned by the current user.

The command prompt returns after the jobs are complete or after the jobs enter an error state.
The output of the **Get-BitsTransfer** cmdlet is a set of BitsJob objects.
This output is piped to the **Resume-BitsTransfer** cmdlet.
If any of the BITS transfer jobs are already active, they will continue to run.

### EXAMPLE 2
```
PS C:\>$b = Start-BitsTransfer -DisplayName "MyJob" -Suspended
PS C:\>Add-BitsTransfer -BitsJob $b -ClientFileName C:\myFile -ServerFileName http://www.mysite.com/file1
PS C:\>Resume-BitsTransfer -BitsJob $b -Asynchronous
```

This command resumes a new BITS transfer job that was initially suspended, and it returns the command prompt immediately.

The first command creates a new BitsJob object in a suspended state and then stores it in the $b variable.

The second command adds a file to the transfer queue of the new BitsJob object that is stored in the $b variable.

The third command uses the **BitsJob** parameter to pass the BitsJob object that is stored in the $b parameter to the **Resume-BitsTransfer** cmdlet.
This command starts the BITS transfer job.

### EXAMPLE 3
```
PS C:\>Get-BitsTransfer -Name testjob1 | Resume-BitsTransfer
```

This command resumes the BITS transfer that is identified by the specified display name.

The command prompt returns after the job is complete or after the job enters an error state.
The output of the **Get-BitsTransfer** cmdlet is a BitsJob object.
This output is piped to the **Resume-BitsTransfer** cmdlet.
If the BITS transfer job is already active, it will continue to run.

## PARAMETERS

### -Asynchronous
Allows the BITS transfer job to be processed in the background.
The command prompt reappears immediately after the BITS transfer job is resumed.
The returned BitsJob object can be used to monitor status and progress.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: as

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BitsJob
Specifies the BITS transfer jobs to resume.
You can pipe a value to this parameter from other cmdlets that return BitsJob objects, such as **Get-BitsTransfer**.

```yaml
Type: BitsJob[]
Parameter Sets: (All)
Aliases: b

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.BackgroundIntelligentTransfer.Management.BitsJob[]
This cmdlet accepts one or more BitsJob objects as input that populates the BitsJob parameter.

## OUTPUTS

### Microsoft.BackgroundIntelligentTransfer.Management.BitsJob[]
When called with the **Asynchronous** parameter, this cmdlet sends the BitsJob object that is associated with the resumed BITS transfer job as output.
Otherwise, no output is generated.

## NOTES
* You can cancel a transfer job that is running in synchronous mode (foreground priority) by pressing CTRL+C.

## RELATED LINKS

[Add-BitsFile](./Add-BitsFile.md)

[Complete-BitsTransfer](./Complete-BitsTransfer.md)

[Get-BitsTransfer](./Get-BitsTransfer.md)

[Remove-BitsTransfer](./Remove-BitsTransfer.md)

[Set-BitsTransfer](./Set-BitsTransfer.md)

[Start-BitsTransfer](./Start-BitsTransfer.md)

[Suspend-BitsTransfer](./Suspend-BitsTransfer.md)

