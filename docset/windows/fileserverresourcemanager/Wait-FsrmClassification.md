---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FSRMClassification.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Wait-FsrmClassification
ms.reviewer:
ms.assetid: 0B23DF39-82FD-41C2-906E-34E6C717B447
---

# Wait-FsrmClassification

## SYNOPSIS
Waits for a period of time or until classification is finished running.

## SYNTAX

```
Wait-FsrmClassification [-Timeout <Int32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Wait-FsrmClassification** cmdlet waits for a period of time or until classification is finished running.
The cmdlet returns when the server finishes running the classification process or when the time that you specify in the *Timeout* parameter has elapsed.

## EXAMPLES

### Example 1: Wait for a classification
```
PS C:\> Start-FsrmClassification
PS C:\> Wait-FsrmClassification
```

The first command starts the classification.

The second command waits for the classification to finish running.

### Example 2: Wait for and stop the classification
```
The first command starts the classification process.
PS C:\> Start-FsrmClassification

The second command waits for the classification to finish running. If the classification is not completed in 10 minutes, the server ends the classification process and the cmdlet returns.
PS C:\> Wait-FsrmClassification -Timeout 600

The third command ensures that the classification has stopped running.
PS C:\> Stop-FsrmClassification
```

This example waits for the classification to finish running and then stops the classification.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete. 

The cmdlet immediately returns an object that represents the job and then displays the command prompt. 
You can continue to work in the session while the job completes. 
To manage the job, use the `*-Job` cmdlets. 
To get the job results, use the [Receive-Job](http://go.microsoft.com/fwlink/?LinkID=113372) cmdlet. 

For more information about Windows PowerShell background jobs, see [about_Jobs](http://go.microsoft.com/fwlink/?LinkID=113251).

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
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Specifies the number of seconds to wait for classification and the reports to complete.
The cmdlet returns when the period expires or classification completes.
To wait indefinitely, set the value to -1.
The value must be in the range from -1 through 2,147,483.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMClassification

## NOTES

## RELATED LINKS

[Get-FsrmClassification](./Get-FsrmClassification.md)

[Set-FsrmClassification](./Set-FsrmClassification.md)

[Start-FsrmClassification](./Start-FsrmClassification.md)

[Stop-FsrmClassification](./Stop-FsrmClassification.md)

