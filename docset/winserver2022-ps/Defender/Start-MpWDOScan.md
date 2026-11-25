---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_MpWDOScan.cdxml-help.xml
Module Name: Defender
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/defender/start-mpwdoscan?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-MpWDOScan
---

# Start-MpWDOScan

## SYNOPSIS
Starts a Windows Defender offline scan.

## SYNTAX

```
Start-MpWDOScan
 [-AsJob]
 [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Start-MpWDOScan** cmdlet starts a Windows Defender offline scan on a computer.

## EXAMPLES

### Example 1: Start an offline scan
```powershell
PS C:\>Start-MpWDOScan
```

This command starts a Windows Defender offline scan on the computer where you run the command.
This command causes the computer to start in Windows Defender offline and begin the scan.

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
