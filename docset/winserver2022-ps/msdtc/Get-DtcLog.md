---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_DtcLogTask_v1.0.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-DtcLog
ms.reviewer:
ms.assetid: 98B9E36F-285E-45AF-BA09-9049F0AD2852
---

# Get-DtcLog

## SYNOPSIS
Gets DTC log file settings.

## SYNTAX

```
Get-DtcLog [-DtcName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DtcLog** cmdlet gets the log file settings for a Distributed Transaction Coordinator (DTC) instance.
Use the **DtcName** parameter to specify a DTC instance.

## EXAMPLES

### Example 1: Get the log file settings for the local DTC instance
```
PS C:\> Get-DtcLog
MaxSizeInMB      : 512
Path             : C:\Windows\system32\MSDtc
SizeInMB         : 4
```

This command gets the DTC log file settings for the local DTC instance.

### Example 2: Get the log file settings for a specified DTC instance
```
PS C:\> Get-DtcLog -DtcName "InstanceName"
MaxSizeInMB      : 512
Path             : G:\MSDTC\beb6d145-405e-47cd-b326-a5505a461229
SizeInMB         : 4
```

This command gets the DTC log file settings for the specified DTC instance.

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

### -DtcName
Specifies a DTC instance.
The cmdlet displays log file settings for this instance.
If you do not specify this parameter, or if you specify a value of Local, the log file settings for the local DTC instance are displayed.

```yaml
Type: String
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Reset-DtcLog](./Reset-DtcLog.md)

[Set-DtcLog](./Set-DtcLog.md)

