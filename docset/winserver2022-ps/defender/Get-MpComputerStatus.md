---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_MpComputerStatus.cdxml-help.xml
Module Name: Defender
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-MpComputerStatus
---

# Get-MpComputerStatus

## SYNOPSIS
Gets the status of antimalware software on the computer.

## SYNTAX

```
Get-MpComputerStatus [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-MpComputerStatus** cmdlet gets the status of antimalware software installed on the computer.

## EXAMPLES

### Example 1: Get the computer status
```
PS C:\> Get-MpComputerStatus
AMEngineVersion                  : 1.1.19700.3
AMProductVersion                 : 4.18.2209.7
AMRunningMode                    : Normal
AMServiceEnabled                 : True
AMServiceVersion                 : 4.18.2209.7
AntispywareEnabled               : True
AntispywareSignatureAge          : 0
AntispywareSignatureLastUpdated  : 18-10-2022 09:18:29 AM
AntispywareSignatureVersion      : 1.377.418.0
AntivirusEnabled                 : True
AntivirusSignatureAge            : 0
AntivirusSignatureLastUpdated    : 18-10-2022 09:18:29 AM
AntivirusSignatureVersion        : 1.377.418.0
BehaviorMonitorEnabled           : True
ComputerID                       : 2142F9EE-BFB8-42DB-BAE6-1B62B3FBD944
ComputerState                    : 0
DefenderSignaturesOutOfDate      : False
DeviceControlDefaultEnforcement  : Unknown
DeviceControlPoliciesLastUpdated : 17-10-2022 08:09:12 PM
DeviceControlState               : Disabled
FullScanAge                      : 4294967295
FullScanEndTime                  :
FullScanOverdue                  : False
FullScanRequired                 : False
FullScanSignatureVersion         :
FullScanStartTime                :
IoavProtectionEnabled            : True
IsTamperProtected                : True
IsVirtualMachine                 : False
LastFullScanSource               : 0
LastQuickScanSource              : 2
NISEnabled                       : True
NISEngineVersion                 : 1.1.19700.3
NISSignatureAge                  : 0
NISSignatureLastUpdated          : 18-10-2022 09:18:29 AM
NISSignatureVersion              : 1.377.418.0
OnAccessProtectionEnabled        : True
ProductStatus                    : 524288
QuickScanAge                     : 1
QuickScanEndTime                 : 16-10-2022 07:06:42 PM
QuickScanOverdue                 : False
QuickScanSignatureVersion        : 1.377.319.0
QuickScanStartTime               : 16-10-2022 07:04:19 PM
RealTimeProtectionEnabled        : True
RealTimeScanDirection            : 0
RebootRequired                   : False
SmartAppControlExpiration        :
SmartAppControlState             : Off
TamperProtectionSource           : UI
TDTMode                          : cm
TDTStatus                        : Enabled
TDTTelemetry                     : Disabled
TroubleShootingDailyMaxQuota     :
TroubleShootingDailyQuotaLeft    :
TroubleShootingEndTime           :
TroubleShootingExpirationLeft    :
TroubleShootingMode              :
TroubleShootingModeSource        :
TroubleShootingQuotaResetTime    :
TroubleShootingStartTime         :
PSComputerName                   :
```

This command gets the status of antimalware protection software installed on the computer.

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
[Get-MpComputerStatus Properties](/previous-versions/windows/desktop/defender/msft-mpcomputerstatus#properties)
