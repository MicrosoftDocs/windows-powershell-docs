---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_MpComputerStatus.cdxml-help.xml
Module Name: Defender
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-MpComputerStatus
---

# Get-MpComputerStatus

## SYNOPSIS
Gets the status of antimalware software on the computer.

## SYNTAX

```
Get-MpComputerStatus [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
[<CommonParameters>]
```

## DESCRIPTION

The `Get-MpComputerStatus` cmdlet gets the status of antimalware software installed on the
computer.

## EXAMPLES

### Example 1: Get the computer status

```
PS C:\> Get-MpComputerStatus
AMEngineVersion                 : 1.1.9700.0
AMProductVersion                : 4.3.9463.0
AMServiceEnabled                : True
AMServiceVersion                : 4.3.9463.0
AntispywareEnabled              : True
AntispywareSignatureAge         : 0
AntispywareSignatureLastUpdated : 7/30/2013 3:01:45 AM
AntispywareSignatureVersion     : 1.155.1107.0
AntivirusEnabled                : True
AntivirusSignatureAge           : 0
AntivirusSignatureLastUpdated   : 7/30/2013 3:01:45 AM
AntivirusSignatureVersion       : 1.155.1107.0
BehaviorMonitorEnabled          : True
ComputerID                      : A69DA5B8-06B3-4A00-B2C1-D18ED66BAD40
ComputerState                   : 0
FullScanAge                     : 4294967295
FullScanEndTime                 :
FullScanStartTime               :
IoavProtectionEnabled           : True
LastFullScanSource              : 0
LastQuickScanSource             : 2
NISEnabled                      : False
NISEngineVersion                : 2.1.9700.0
NISSignatureAge                 : 0
NISSignatureLastUpdated         : 7/30/2013 1:30:46 PM
NISSignatureVersion             : 106.0.0.0
OnAccessProtectionEnabled       : True
QuickScanAge                    : 0
QuickScanEndTime                : 7/30/2013 1:50:24 PM
QuickScanStartTime              : 7/30/2013 1:49:15 PM
RealTimeProtectionEnabled       : True
RealTimeScanDirection           : 0
```

This command gets the status of antimalware protection software installed on the computer.

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

The cmdlet immediately returns an object that represents the job and then displays the command
prompt. You can continue to work in the session while the job completes. To manage the job, use the
`*-Job` cmdlets. To get the job results, use the
[Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see
[about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967)
or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. The default is the
current session on the local computer.

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

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216). ## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-MpComputerStatus Properties](/previous-versions/windows/desktop/defender/msft-mpcomputerstatus#properties)
