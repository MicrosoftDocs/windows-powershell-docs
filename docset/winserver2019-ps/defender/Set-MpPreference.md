---
description: Use this article to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_MpPreference.cdxml-help.xml
Module Name: Defender
ms.date: 03/22/2023
online version: https://learn.microsoft.com/powershell/module/defender/set-mppreference?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-MpPreference
---

# Set-MpPreference

## SYNOPSIS
Configures preferences for Windows Defender scans and updates.

## SYNTAX

```
Set-MpPreference [-ExclusionPath <String[]>] [-ExclusionExtension <String[]>] [-ExclusionProcess <String[]>]
 [-RealTimeScanDirection <ScanDirection>] [-QuarantinePurgeItemsAfterDelay <UInt32>]
 [-RemediationScheduleDay <Day>] [-RemediationScheduleTime <DateTime>]
 [-ReportingAdditionalActionTimeOut <UInt32>] [-ReportingCriticalFailureTimeOut <UInt32>]
 [-ReportingNonCriticalTimeOut <UInt32>] [-ScanAvgCPULoadFactor <Byte>]
 [-CheckForSignaturesBeforeRunningScan <Boolean>] [-ScanPurgeItemsAfterDelay <UInt32>]
 [-ScanOnlyIfIdleEnabled <Boolean>] [-ScanParameters <ScanType>] [-ScanScheduleDay <Day>]
 [-ScanScheduleQuickScanTime <DateTime>] [-ScanScheduleOffset <UInt32>] [-SignatureFirstAuGracePeriod <UInt32>]
 [-ScanScheduleTime <HH:MM:SS>] [-AllowSwitchToAsyncInspection <Boolean>]
 [-SignatureAuGracePeriod <UInt32>] [-SignatureDefinitionUpdateFileSharesSources <String>]
 [-SignatureDisableUpdateOnStartupWithoutEngine <Boolean>] [-SignatureFallbackOrder <String>]
 [-SignatureScheduleDay <Day>] [-SignatureScheduleTime <DateTime>] [-SignatureUpdateCatchupInterval <UInt32>]
 [-SignatureUpdateInterval <UInt32>] [-MAPSReporting <MAPSReportingType>]
 [-SubmitSamplesConsent <SubmitSamplesConsentType>] [-DisableAutoExclusions <Boolean>]
 [-DisablePrivacyMode <Boolean>] [-RandomizeScheduleTaskTimes <Boolean>] [-DisableBehaviorMonitoring <Boolean>]
 [-DisableIntrusionPreventionSystem <Boolean>] [-DisableIOAVProtection <Boolean>]
 [-DisableRealtimeMonitoring <Boolean>] [-DisableScriptScanning <Boolean>] [-DisableArchiveScanning <Boolean>]
 [-DisableCatchupFullScan <Boolean>] [-DisableCatchupQuickScan <Boolean>] [-DisableCpuThrottleOnIdleScans <Boolean>] [-DisableEmailScanning <Boolean>]
 [-DisableEmailScanning <Boolean>]
 [-DisableRemovableDriveScanning <Boolean>] [-DisableRestorePoint <Boolean>]
 [-DisableScanningMappedNetworkDrivesForFullScan <Boolean>] [-DisableScanningNetworkFiles <Boolean>]
 [-UILockdown <Boolean>] [-ThreatIDDefaultAction_Ids <Int64[]>]
 [-ThreatIDDefaultAction_Actions <ThreatAction[]>] [-UnknownThreatDefaultAction <ThreatAction>]
 [-LowThreatDefaultAction <ThreatAction>] [-ModerateThreatDefaultAction <ThreatAction>]
 [-HighThreatDefaultAction <ThreatAction>] [-SevereThreatDefaultAction <ThreatAction>] [-Force]
 [-DisableBlockAtFirstSeen <Boolean>] [-PUAProtection <PUAProtectionType>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob]  [<CommonParameters>]
 [-DisableGradualRelease <Boolean>] [-DefinitionUpdatesChannel <UpdatesChannelType>] [-EngineUpdatesChannel <UpdatesChannelType>] [-PlatformUpdatesChannel <UpdatesChannelType>][-CloudBlockLevel <CloudBlockLevelType>][-ServiceHealthReportInterval <UInt32>]
 ```

## DESCRIPTION
The **Set-MpPreference** cmdlet configures preferences for Windows Defender scans and updates.
You can modify exclusion file name extensions, paths, or processes, and specify the default action for high, moderate, and low threat levels.

**REMEDIATION VALUES**

The following table provides remediation action values for detected threats at low, medium, high, and severe alert levels.

|Value |Action |
|------|-------------------|
|1 |Clean the detected threat. |
|2 |Quarantine the detected threat. |
|3 |Remove the detected threat. |
|6 |Allow the detected threat. |
|8 |Allow the user to determine the action to take with the detected threat. |
|9 |Don’t take any action. |
|10 |Block the detected threat. |
|0 | (NULL)|Apply action based on the Security Intelligence Update (SIU). This value is the default value. |

## EXAMPLES

### Example 1: Schedule to check for definition updates everyday

```
PS C:\> Set-MpPreference -SignatureScheduleDay Everyday
```

This command configures preferences to check for definition updates every day.

### Example 2: Schedule a time of day to check for definition updates

```
PS C:\> Set-MpPreference -SignatureScheduleTime 02:00:00
```

This command configures preferences to check for definition updates 120 minutes after midnight on days when it’s scheduled to check.

## PARAMETERS

### -AllowSwitchToAsyncInspection

Specifies whether to enable a performance optimization that allows synchronously inspected network flows to switch to async inspection once they have been checked and validated.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Enabled
Accept pipeline input: False
Accept wildcard characters: False
```


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

### -CheckForSignaturesBeforeRunningScan
Indicates whether to check for new virus and spyware definitions before Windows Defender runs a scan.
If you specify a value of `$True`, Windows Defender checks for new definitions.
If you specify `$False` or don’t specify a value, the scan begins with existing definitions.
This setting applies to scheduled scans, but it has no effect on scans initiated manually from the user interface or on scans started from the command line using "mpcmdrun -Scan".

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: csbr

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

### -CloudBlockLevel
Configure this policy to specify the level of cloud protection to your endpoint. 

- Default (0): provides strong detection without increasing risk of detecting legitimate files
- Moderate (1): provides moderate detection only for high confidence detections
- High (2): applies a strong level of detection while optimizing client performance
- HighPlus (4): applies extra protection measures (might affect client performance and increase your chance of false positives)
- ZeroTolerance (6): blocks all unknown executables

```yaml
Type: CloudBlockLevelType
Accepted values: Default|Moderate|High|HighPlus|ZeroTolerance
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### -DefinitionUpdatesChannel
Enable this policy to specify when devices receive daily Microsoft Defender security intelligence (definition/signature) updates during the daily gradual rollout. 

Current Channel (Staged): Devices will be offered updates after the release cycle. Suggested to apply to a small, representative part of production population (~10%).

Current Channel (Broad): Devices will be offered updates only after the gradual release cycle completes. Suggested to apply to a broad set of devices in your production population (~10-100%). 

If you disable or don’t configure this policy, the device will stay up to date automatically during the daily release cycle. Suitable for most devices. 

Supported OS versions: Windows 10 

Note: This policy is available starting with platform version 4.18.2106.5 and later

```yaml
Type: UpdatesChannelType
Aliases: suc
Accepted values: Staged|Broad|Not Configured
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableArchiveScanning
Indicates whether to scan archive files, such as .zip and .cab files, for malicious and unwanted software.
If you specify a value of `$False` or don’t specify a value, Windows Defender scans archive files.
However, archives are always scanned during directed scans.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: darchsc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableAutoExclusions
Indicates whether to disable the Automatic Exclusions feature for the server.
If you specify a value of `$False` or don’t specify a value, Windows Defender enables the Automatic Exclusions feature for the server.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dae

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableBehaviorMonitoring
Indicates whether to enable behavior monitoring.
If you specify a value of `$False` or don’t specify a value, Windows Defender enables behavior monitoring.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dbm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableBlockAtFirstSeen
Indicates whether to enable block at first seen.
If you specify a value of `$False` or don’t specify a value, Windows Defender enables block at first seen.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dbaf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableCatchupFullScan
Indicates whether Windows Defender runs catch-up scans for scheduled full scans.
A computer can miss a scheduled scan, usually because the computer is turned off at the scheduled time.
If you specify a value of `$False`, after the computer misses two scheduled full scans, Windows Defender runs a catch-up scan the next time someone signs in the computer. If you specify a value of `$True`, the computer doesn’t run catch-up scans for scheduled full scans.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dcfsc

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableCatchupQuickScan
Indicates whether Windows Defender runs catch-up scans for scheduled quick scans.
A computer can miss a scheduled scan, usually because the computer is off at the scheduled time.
If you specify a value of `$False`, after the computer misses two scheduled quick scans, Windows Defender runs a catch-up scan the next time someone signs in the computer. If you specify a value of `$True`, the computer doesn’t run catch-up scans for scheduled quick scans.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dcqsc

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableCpuThrottleOnIdleScans
Indicates whether the CPU will be throttled for scheduled scans while the device is idle. This parameter is enabled by default, thus ensuring that the CPU won’t be throttled for scheduled scans performed when the device is idle, regardless of what **ScanAvgCPULoadFactor** is set to. For all other scheduled scans, this flag doesn’t have any impact and normal throttling will occur.

```yaml
Type: Boolean
Aliases: None
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableEmailScanning
Indicates whether Windows Defender parses the mailbox and mail files, according to their specific format, in order to analyze mail bodies and attachments.
Windows Defender supports several formats, including .pst, .dbx, .mbx, .mime, and .binhex.
If you specify a value of `$False` or don’t specify a value, Windows Defender performs email scanning. If you specify a value of `$True`, Windows Defender doesn’t perform email scanning.
This configuration isn’t applicable to modern email clients.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: demsc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableGradualRelease

Enable this policy to disable gradual rollout of monthly and daily Defender updates. 

Devices will be offered all Defender updates after the gradual release cycle completes. Best for datacenter machines that only receive limited updates. 

Note: This setting applies to both monthly and daily Defender updates and will override any previously configured channel selections for platform and engine updates. 

If you disable or don’t configure this policy, the device will remain in Current Channel (Default) unless specified otherwise in specific channels for platform and engine updates. Stay up to date automatically during the gradual release cycle. Suitable for most devices. 

Supported OS versions: Windows 10 

Note: This policy is available starting with platform version 4.18.2106.5 and later

```yaml
Type: Boolean
Aliases: dgr
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableIOAVProtection
Indicates whether Windows Defender scans all downloaded files and attachments.
If you specify a value of `$False` or don’t specify a value, scanning downloaded files and attachments is enabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dioavp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableIntrusionPreventionSystem
This parameter was deprecated and its use has no impact.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dips

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisablePrivacyMode
Indicates whether to disable privacy mode.
Privacy mode prevents users, other than administrators, from displaying threat history.
If you specify a value of `$False` or don’t specify a value, privacy mode is enabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dpm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableRealtimeMonitoring
Indicates whether to use real-time protection.
If you specify a value of `$False` or don’t specify a value, Windows Defender uses real-time protection.
We recommend that you enable Windows Defender to use real-time protection.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: drtm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableRemovableDriveScanning
Indicates whether to scan for malicious and unwanted software in removable drives, such as flash drives, during a full scan.
If you specify a value of `$False` or don’t specify a value, Windows Defender scans removable drives during any type of scan. If you specify a value of `$True`, Windows Defender doesn’t scan removable drives during a full scan. Windows Defender can still scan removable drives during quick scans or custom scans.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: drdsc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableRestorePoint
Indicates whether to disable scanning of restore points.
If you specify a value of `$False` or don’t specify a value, Windows Defender restore point is enabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: drp, dsnf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableScanningMappedNetworkDrivesForFullScan
Indicates whether to scan mapped network drives. If you specify a value of `$False` or don’t specify a value, Windows Defender scans mapped network drives. If you specify a value of `$True`, Windows Defender doesn’t scan mapped network drives.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dsmndfsc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableScanningNetworkFiles
Indicates whether to scan for network files. If you specify a value of `$False` or don’t specify a value, Windows Defender scans network files. If you specify a value of `$True`, Windows Defender doesn’t scan network files. We don’t recommend scanning network files.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dsnf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableScriptScanning
Specifies whether to disable the scanning of scripts during malware scans.
If you specify a value of `$False` or don’t specify a value, Windows Defender doesn’t scan scripts.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dscrptsc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EngineUpdatesChannel 

Enable this policy to specify when devices receive Microsoft Defender engine updates during the monthly gradual rollout. 

Beta Channel: Devices set to this channel will be the first to receive new updates. Select Beta Channel to participate in identifying and reporting issues to Microsoft. Devices in the Windows Insider Program are subscribed to this channel by default. For use in (manual) test environments only and a limited number of devices. 

Current Channel (Preview): Devices set to this channel will be offered updates earliest during the monthly gradual release cycle. Suggested for pre-production/validation environments. 

Current Channel (Staged): Devices will be offered updates after the monthly gradual release cycle. Suggested to apply to a small, representative part of your production population (~10%). 

Current Channel (Broad): Devices will be offered updates only after the gradual release cycle completes. Suggested to apply to a broad set of devices in your production population (~10-100%). 

Critical- Time Delay: Devices will be offered updates with a 48-hour delay. Suggested for critical environments only.   

If you disable or don’t configure this policy, the device will stay up to date automatically during the gradual release cycle. Suitable for most devices. 

Supported OS versions: Windows 10 
Note: This policy is available starting with platform version 4.18.2106.5 and later

```yaml
Type: UpdatesChannelType
Aliases: euc
Accepted values:Beta|Preview|Staged|Broad|Delayed|NotConfigured 
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExclusionExtension
Specifies an array of file name extensions, such as obj or lib, to exclude from scheduled, custom, and real-time scanning.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExclusionPath
Specifies an array of file paths to exclude from scheduled and real-time scanning.
You can specify a folder to exclude all the files under the folder.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExclusionProcess
Specifies an array of processes, as paths to process images.
This cmdlet excludes any files opened by the processes that you specify from scheduled and real-time scanning.
Specifying this parameter excludes files opened by executable programs only.
The cmdlet doesn’t exclude the processes themselves.
To exclude a process, specify it by using the **ExclusionPath** parameter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -HighThreatDefaultAction
Specifies which automatic remediation action to take for a high-level threat.
The acceptable values for this parameter are:

- Quarantine 
- Remove 
- Ignore

```yaml
Type: ThreatAction
Parameter Sets: (All)
Aliases: htdefac
Accepted values: Clean, Quarantine, Remove, Allow, UserDefined, NoAction, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LowThreatDefaultAction
Specifies which automatic remediation action to take for a low-level threat.
The acceptable values for this parameter are:

- Quarantine 
- Remove 
- Ignore

```yaml
Type: ThreatAction
Parameter Sets: (All)
Aliases: ltdefac
Accepted values: Clean, Quarantine, Remove, Allow, UserDefined, NoAction, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MAPSReporting
Specifies the type of membership in Microsoft Active Protection Service.
Microsoft Active Protection Service is an online community that helps you choose how to respond to potential threats.
The community also helps prevent the spread of new malicious software.
The acceptable values for this parameter are:

- 0: Disabled - Send no information to Microsoft. This value is the default value. 
- 1: Basic membership. - Send basic information to Microsoft about detected software, including where the software came from, the actions that you apply or that apply automatically, and whether the actions succeeded. 
- 2: Advanced membership. - In addition to basic information, send more information to Microsoft about malicious software, spyware, and potentially unwanted software, including the location of the software, file names, how the software operates, and how it affects your computer.

If you join this community, you can choose to automatically send basic or additional information about detected software.

Additional information helps Microsoft create new definitions.

In some instances, personal information might unintentionally be sent to Microsoft.
However, Microsoft won’t use this information to identify you or contact you.

```yaml
Type: MAPSReportingType
Parameter Sets: (All)
Aliases: 
Accepted values: Disabled, Basic, Advanced

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModerateThreatDefaultAction
Specifies which automatic remediation action to take for a moderate level threat.
The acceptable values for this parameter are:

- Quarantine 
- Remove 
- Ignore

```yaml
Type: ThreatAction
Parameter Sets: (All)
Aliases: mtdefac
Accepted values: Clean, Quarantine, Remove, Allow, UserDefined, NoAction, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PUAProtection

```yaml
Type: PUAProtectionType
Parameter Sets: (All)
Aliases: 
Accepted values: Disabled, Enabled, AuditMode

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PlatformUpdatesChannel 

Enable this policy to specify when devices receive Microsoft Defender platform updates during the monthly gradual rollout.

Beta Channel: Devices set to this channel will be the first to receive new updates. Select Beta Channel to participate in identifying and reporting issues to Microsoft. Devices in the Windows Insider Program are subscribed to this channel by default. For use in (manual) test environments only and a limited number of devices. 

Current Channel (Preview): Devices set to this channel will be offered updates earliest during the monthly gradual release cycle. Suggested for pre-production/validation environments. 

Current Channel (Staged): Devices will be offered updates after the monthly gradual release cycle. Suggested to apply to a small, representative part of your production population (~10%). 

Current Channel (Broad): Devices will be offered updates only after the gradual release cycle completes. Suggested to apply to a broad set of devices in your production population (~10-100%). 

Critical- Time Delay: Devices will be offered updates with a 48-hour delay. Suggested for critical environments only.   

If you disable or don’t configure this policy, the device will stay up to date automatically during the gradual release cycle. Suitable for most devices. 

Supported OS versions: Windows 10 

Note: This policy is available starting with platform version 4.18.2106.5 and later

```yaml
Type: UpdatesChannelType
Aliases: puc
Accepted values: Beta|Preview|Staged|Broad|Delayed|NotConfigured 
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QuarantinePurgeItemsAfterDelay
Specifies the number of days to keep items in the Quarantine folder.
If you specify a value of zero or don’t specify a value for this parameter, items stay in the Quarantine folder indefinitely.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: qpiad

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RandomizeScheduleTaskTimes
Indicates whether to select a random time for the scheduled start and scheduled update for definitions.
If you specify a value of `$True` or don’t specify a value, scheduled tasks begin within 30 minutes, before or after, the scheduled time.
If you randomize the start times, it can distribute the impact of scanning.
For example, if several virtual machines share the same host, randomized start times prevents all the hosts from starting the scheduled tasks at the same time.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: rstt

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RealTimeScanDirection
Specifies scanning configuration for incoming and outgoing files on NTFS volumes.
The acceptable values for this parameter are:

- 0: Scan both incoming and outgoing files.
This is the default. 
- 1: Scan incoming files only. 
- 2: Scan outgoing files only. 

Specify a value for this parameter to enhance performance on servers that have a large number of file transfers, but need scanning for either incoming or outgoing files.
Evaluate this configuration based on the server role.
For non-NTFS volumes, Windows Defender performs full monitoring of file and program activity.

```yaml
Type: ScanDirection
Parameter Sets: (All)
Aliases: rtsd
Accepted values: Both, Incoming, Outcoming

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemediationScheduleDay
Specifies the day of the week on which to perform a scheduled full scan in order to complete remediation.
Alternatively, specify everyday for this full scan or never.
The acceptable values for this parameter are:

- 0: Everyday
- 1: Sunday
- 2: Monday
- 3: Tuesday 
- 4: Wednesday
- 5: Thursday 
- 6: Friday
- 7: Saturday
- 8: Never 

The default value is 8, never.
If you specify a value of 8 or don’t specify a value, Windows Defender performs a scheduled full scan to complete remediation by using a default frequency.

```yaml
Type: Day
Parameter Sets: (All)
Aliases: rsd
Accepted values: Everyday, Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemediationScheduleTime
Specifies the time of day, as the number of minutes after midnight, to perform a scheduled scan.
The time refers to the local time on the computer.
If you don’t specify a value for this parameter, a scheduled scan runs at the default time of two hours after midnight.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: rst

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportingAdditionalActionTimeOut
Specifies the number of minutes before a detection in the additional action state changes to the cleared state.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: raat

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportingCriticalFailureTimeOut
Specifies the number of minutes before a detection in the critically failed state changes to either the additional action state or the cleared state.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: rcto

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportingNonCriticalTimeOut
Specifies the number of minutes before a detection in the non-critically failed state changes to the cleared state.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: rncto

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScanAvgCPULoadFactor
Specifies the maximum percentage CPU usage for a scan.
The acceptable values for this parameter are: integers from 5 through 100, and the value 0, which disables CPU throttling.
Windows Defender doesn’t exceed the percentage of CPU usage that you specify.
The default value is 50.

Note: This limit isn’t a hard limit but rather guidance for the scanning engine to not exceed this maximum on average.

Note: Manually run scans will ignore this setting and run without any CPU limits.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: saclf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScanOnlyIfIdleEnabled
Indicates whether to start scheduled scans only when the computer isn’t in use.
If you specify a value of `$True` or don’t specify a value, Windows Defender runs schedules scans when the computer is on, but not in use.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: soiie

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScanParameters
Specifies the scan type to use during a scheduled scan.
The acceptable values for this parameter are:

- 1: Quick scan
- 2: Full scan 

If you don’t specify this parameter, Windows Defender uses the default value of quick scan.

```yaml
Type: ScanType
Parameter Sets: (All)
Aliases: 
Accepted values: QuickScan, FullScan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScanPurgeItemsAfterDelay
Specifies the number of days to keep items in the scan history folder.
After this time, Windows Defender removes the items.
If you specify a value of zero, Windows Defender doesn’t remove items.
If you don’t specify a value, Windows Defender removes items from the scan history folder after the default length of time, which is 15 days.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: spiad

Required: False
Position: Named
Default value: 15
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScanScheduleDay
Specifies the day of the week on which to perform a scheduled scan.
Alternatively, specify everyday for a scheduled scan or never.
The acceptable values for this parameter are:

- 0: Everyday 
- 1: Sunday 
- 2: Monday 
- 3: Tuesday 
- 4: Wednesday 
- 5: Thursday 
- 6: Friday 
- 7: Saturday 
- 8: Never

The default value is 8, never.
If you specify a value of 8 or don’t specify a value, Windows Defender doesn’t perform scheduled scans.

```yaml
Type: Day
Parameter Sets: (All)
Aliases: scsd
Accepted values: Everyday, Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScanScheduleQuickScanTime
Specifies the time of day, as the number of minutes after midnight, to perform a scheduled quick scan.
The time refers to the local time on the computer.
If you don’t specify a value for this parameter, a scheduled quick scan runs at the time specified by the **ScanScheduleOffset** parameter.
That parameter has a default time of two hours after midnight.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: scsqst

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScanScheduleOffset
Configures the number of minutes after midnight to perform a scheduled scan. The time on the endpoint is used to determine the local time. If you enable this setting, a scheduled scan will run at the time specified. If you disable or don’t enable this setting, a scheduled scan runs at the default time of two hours (120 minutes) after midnight.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: scso

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScanScheduleTime
Specifies the time of day to run a scheduled scan. The time refers to the local time on the computer. Specify the number of minutes after midnight (for example, enter 60 for 1 a.m.). This parameter has a default time of two hours after midnight (2 a.m.).

```yaml
Type: DateTime
Aliases: scsqst
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceHealthReportInterval
This policy setting configures the time interval (in minutes) for the service health reports to be sent from endpoints. These are for Microsoft Defender Antivirus events 1150 and 1151. For more information, see [Microsoft Defender Antivirus event IDs](/microsoft-365/security/defender-endpoint/troubleshoot-microsoft-defender-antivirus#microsoft-defender-antivirus-event-ids).

If you don’t configure this setting, the default value will be applied. The default value is set at 60 minutes (one hour). 
If you configure this setting to 0, no service health reports will be sent.
The maximum value allowed to be set is 14400 minutes (10 days).

```yaml
Type: UInt32
Aliases: shri
Accepted values: 0-14400
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### -SevereThreatDefaultAction
Specifies which automatic remediation action to take for a severe level threat.
The acceptable values for this parameter are:

- Quarantine 
- Remove 
- Ignore

```yaml
Type: ThreatAction
Parameter Sets: (All)
Aliases: stdefac
Accepted values: Clean, Quarantine, Remove, Allow, UserDefined, NoAction, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureAuGracePeriod
Specifies a grace period, in minutes, for the definition.
If a definition successfully updates within this period, Windows Defender abandons any service initiated updates.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: sigagp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureDefinitionUpdateFileSharesSources
Specifies file-share sources for definition updates.
Specify sources as a bracketed sequence of Universal Naming Convention (UNC) locations, separated by the pipeline symbol; for example, `{ \\\\Server01\Share01 | \\\\Server02\Share02 | \\\\Server03\Share03}`.
If you specify a value for this parameter, Windows Defender attempts to connect to the shares in the order that you specify.
After Windows Defender updates a definition, it stops attempting to connect to shares on the list.
If you don’t specify a value for this parameter, the list is empty.

```yaml
Type: String
Parameter Sets: (All)
Aliases: sigdufss

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureDisableUpdateOnStartupWithoutEngine
Indicates whether to initiate definition updates even if no antimalware engine is present.
If you specify a value of `$True` or don’t specify a value, Windows Defender doesn’t initiate definition updates on startup.
If you specify a value of `$False`, and if no antimalware engine is present, Windows Defender initiates definition updates on startup.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: sigduoswo

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureFallbackOrder
Specifies the order in which to contact different definition update sources.
Specify the types of update sources in the order in which you want Windows Defender to contact them, enclosed in braces and separated by the pipeline symbol; for example, `{ InternalDefinitionUpdateServer | MicrosoftUpdateServer | MMPC }`.
The values that you can specify in the string are:

- InternalDefinitionUpdateServer
- MicrosoftUpdateServer
- MMPC
- FileShares

MMPC refers to Microsoft Malware Protection Center.

If you specify a value for this parameter, Windows Defender contacts the definition update sources in the specified order.
After Windows Defender downloads definition updates from a source, it stops attempting to connect to other sources.
If you don’t specify a value for this parameter, Windows Defender contacts sources in the default order of { MicrosoftUpdateServer | MMPC }.

```yaml
Type: String
Parameter Sets: (All)
Aliases: sfo

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureFirstAuGracePeriod
Specifies a grace period, in minutes, for the definition.
If a definition successfully updates within this period, Windows Defender abandons any service initiated updates.
This parameter overrides the value of the **CheckForSignaturesBeforeRunningScan** parameter.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: sigfagp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureScheduleDay
Specifies the day of the week on which to check for definition updates.
Alternatively, specify everyday for a scheduled scan or never.
The acceptable values for this parameter are:

- 0: Everyday 
- 1: Sunday 
- 2: Monday 
- 3: Tuesday 
- 4: Wednesday 
- 5: Thursday 
- 6: Friday 
- 7: Saturday 
- 8: Never 

The default value is 8, never.
If you specify a value of 8 or don’t specify a value, Windows Defender checks for definition updates by using a default frequency.

```yaml
Type: Day
Parameter Sets: (All)
Aliases: sigsd
Accepted values: Everyday, Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureScheduleTime
Specifies the time of day, as the number of minutes after midnight, to check for definition updates.
The time refers to the local time on the computer.
If you don’t specify a value for this parameter, Windows Defender checks for definition updates at the default time of 15 minutes before the scheduled scan time.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: sigst

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureUpdateCatchupInterval
Specifies the number of days after which Windows Defender requires a catch-up definition update.
If you don’t specify a value for this parameter, Windows Defender requires a catch-up definition update after the default value of one day.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: siguci

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### -SignatureUpdateInterval
Specifies the interval, in hours, at which to check for definition updates.
The acceptable values for this parameter are: integers from 1 through 24.
If you don’t specify a value for this parameter, Windows Defender checks at the default interval.
You can use this parameter instead of the **SignatureScheduleDay** parameter and **SignatureScheduleTime** parameter.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: sigui

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubmitSamplesConsent
Specifies how Windows Defender checks for user consent for certain samples.
If consent has previously been granted, Windows Defender submits the samples.
Otherwise, if the **MAPSReporting** parameter doesn’t have a value of Disabled, Windows Defender prompts the user for consent.
The acceptable values for this parameter are:

- 0: Always prompt
- 1: Send safe samples automatically 
- 2: Never send
- 3: Send all samples automatically

```yaml
Type: SubmitSamplesConsentType
Parameter Sets: (All)
Aliases: 
Accepted values: AlwaysPrompt, SendSafeSamples, NeverSend, SendAllSamples

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThreatIDDefaultAction_Actions
Specifies an array of the actions to take for the IDs specified by using the **ThreatIDDefaultAction_Ids** parameter.
The acceptable values for this parameter are:

- 1: Clean 
- 2: Quarantine 
- 3: Remove 
- 6: Allow 
- 8: UserDefined 
- 9: NoAction 
- 10: Block

>[!NOTE]
>A value of 0 (NULL) applies an action based on the Security Intelligence Update (SIU). This is the default value.

```yaml
Type: ThreatAction[]
Parameter Sets: (All)
Aliases: tiddefaca
Accepted values: Clean, Quarantine, Remove, Allow, UserDefined, NoAction, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThreatIDDefaultAction_Ids
Specifies an array of threat IDs.
This cmdlet modifies the default action for the threat IDs that you specify.

```yaml
Type: Int64[]
Parameter Sets: (All)
Aliases: tiddefaci

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

### -UILockdown
Indicates whether to disable UI lockdown mode.
If you specify a value of `$True`, Windows Defender disables UI lockdown mode.
If you specify `$False` or don’t specify a value, UI lockdown mode is enabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UnknownThreatDefaultAction
Specifies which automatic remediation action to take for an unknown level threat.
The acceptable values for this parameter are:

- Quarantine 
- Remove 
- Ignore

```yaml
Type: ThreatAction
Parameter Sets: (All)
Aliases: unktdefac
Accepted values: Clean, Quarantine, Remove, Allow, UserDefined, NoAction, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-MpPreference](./Add-MpPreference.md)

[Get-MpPreference](./Get-MpPreference.md)

[Remove-MpPreference](./Remove-MpPreference.md)
