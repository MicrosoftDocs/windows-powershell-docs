---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_AutologgerConfig_v1.0.cdxml-help.xml
Module Name: EventTracingManagement
ms.date: 01/05/2017
online version: https://learn.microsoft.com/powershell/module/eventtracingmanagement/get-autologgerconfig?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AutologgerConfig
---

# Get-AutologgerConfig

## SYNOPSIS
Enumerates existing AutoLogger session configurations.

## SYNTAX

```
Get-AutologgerConfig [[-Name] <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AutologgerConfig** cmdlet enumerates existing AutoLogger session configurations.

## EXAMPLES

### Example 1: Get a configuration
```
PS C:\> Get-AutologgerConfig -Name "WFP-IPsec Trace"
Name                       : WFP-IPsec Trace
BufferSize                 :
ClockType                  : 2
DisableRealtimePersistence :
FileCount                  :
FileName                   : %SystemRoot%\System32\LogFiles\WMI\wfp.etl
FileMax                    :
FlushTimer                 :
Guid                       : {0762bd13-14d5-4928-9db0-6c4e96312988}
LogFileMode                : 0x1202
MaximumFileSize                : 8
MaximumBuffers             :
MinimumBuffers             :
Start                      : 0
InitStatus                 : 0
```

This command gets the AutoLogger configuration named WFP-IPsec Trace.

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

### -Name
Specifies the name of the AutoLogger session.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Configuring and Starting an AutoLogger Session](https://msdn.microsoft.com/library/windows/desktop/aa363687.aspx)

[Logging Mode Constants](https://msdn.microsoft.com/library/windows/desktop/aa364080.aspx)

[New-AutologgerConfig](./New-AutologgerConfig.md)

[Remove-AutologgerConfig](./Remove-AutologgerConfig.md)

[Update-AutologgerConfig](./Update-AutologgerConfig.md)

