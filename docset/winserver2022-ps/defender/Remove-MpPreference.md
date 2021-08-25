---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_MpPreference.cdxml-help.xml
Module Name: Defender
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/defender/remove-mppreference?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-MpPreference
---

# Remove-MpPreference

## SYNOPSIS
Removes exclusions or default actions.

## SYNTAX

```
Remove-MpPreference [-ExclusionPath <String[]>] [-ExclusionExtension <String[]>] [-ExclusionProcess <String[]>]
 [-ExclusionIpAddress <String[]>] [-RealTimeScanDirection] [-QuarantinePurgeItemsAfterDelay]
 [-RemediationScheduleDay] [-RemediationScheduleTime] [-ReportingAdditionalActionTimeOut]
 [-ReportingCriticalFailureTimeOut] [-ReportingNonCriticalTimeOut] [-ScanAvgCPULoadFactor]
 [-CheckForSignaturesBeforeRunningScan] [-ScanPurgeItemsAfterDelay] [-ScanOnlyIfIdleEnabled] [-ScanParameters]
 [-ScanScheduleDay] [-ScanScheduleQuickScanTime] [-ScanScheduleTime] [-SignatureFirstAuGracePeriod]
 [-SignatureAuGracePeriod] [-SignatureDefinitionUpdateFileSharesSources]
 [-SignatureDisableUpdateOnStartupWithoutEngine] [-SignatureFallbackOrder] [-SharedSignaturesPath]
 [-SignatureScheduleDay] [-SignatureScheduleTime] [-SignatureUpdateCatchupInterval] [-SignatureUpdateInterval]
 [-SignatureBlobUpdateInterval] [-SignatureBlobFileSharesSources] [-MeteredConnectionUpdates]
 [-AllowNetworkProtectionOnWinServer] [-DisableDatagramProcessing] [-DisableCpuThrottleOnIdleScans]
 [-MAPSReporting] [-SubmitSamplesConsent] [-DisableAutoExclusions] [-DisablePrivacyMode]
 [-RandomizeScheduleTaskTimes] [-SchedulerRandomizationTime] [-DisableBehaviorMonitoring]
 [-DisableIntrusionPreventionSystem] [-DisableIOAVProtection] [-DisableRealtimeMonitoring]
 [-DisableScriptScanning] [-DisableArchiveScanning] [-DisableCatchupFullScan] [-DisableCatchupQuickScan]
 [-DisableEmailScanning] [-DisableRemovableDriveScanning] [-DisableRestorePoint]
 [-DisableScanningMappedNetworkDrivesForFullScan] [-DisableScanningNetworkFiles] [-UILockdown]
 [-ThreatIDDefaultAction_Ids <Int64[]>] [-ThreatIDDefaultAction_Actions <ThreatAction[]>]
 [-UnknownThreatDefaultAction] [-LowThreatDefaultAction] [-ModerateThreatDefaultAction]
 [-HighThreatDefaultAction] [-SevereThreatDefaultAction] [-DisableBlockAtFirstSeen] [-PUAProtection]
 [-CloudBlockLevel] [-CloudExtendedTimeout] [-EnableNetworkProtection] [-EnableControlledFolderAccess]
 [-AttackSurfaceReductionOnlyExclusions <String[]>] [-ControlledFolderAccessAllowedApplications <String[]>]
 [-ControlledFolderAccessProtectedFolders <String[]>] [-AttackSurfaceReductionRules_Ids <String[]>]
 [-AttackSurfaceReductionRules_Actions <ASRRuleActionType[]>] [-EnableLowCpuPriority]
 [-EnableFileHashComputation] [-EnableFullScanOnBatteryPower] [-ProxyPacUrl] [-ProxyServer] [-ProxyBypass]
 [-ForceUseProxyOnly] [-DisableTlsParsing] [-DisableHttpParsing] [-DisableDnsParsing]
 [-DisableDnsOverTcpParsing] [-DisableSshParsing] [-PlatformUpdatesChannel] [-EngineUpdatesChannel]
 [-SignaturesUpdatesChannel] [-DisableGradualRelease] [-AllowNetworkProtectionDownLevel]
 [-AllowDatagramProcessingOnWinServer] [-EnableDnsSinkhole] [-DisableInboundConnectionFiltering]
 [-DisableRdpParsing] [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-MpPreference** cmdlet removes exclusions for file name extensions, paths, and processes, or default actions for high, moderate, and low threats.
If you attempt to remove an exclusion that is not in the list, this cmdlet reports the error.

## EXAMPLES

### Example 1: Remove a folder from the exclusion list
```
PS C:\> Remove-MpPreference -ExclusionPath "C:\Temp"
```

This command removes the folder C:\Temp from the exclusion list.

### Example 2: 
```
PS C:\> Remove-MpPreference -AttackSurfaceReductionOnlyExclusions "C:\Windows\App.exe"
```

This command will exclude only that specific file app.exe in that specific folder.

## PARAMETERS

### -AllowDatagramProcessingOnWinServer
{{ Fill AllowDatagramProcessingOnWinServer Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: adpows

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowNetworkProtectionDownLevel
{{ Fill AllowNetworkProtectionDownLevel Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: anpdl

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowNetworkProtectionOnWinServer
{{ Fill AllowNetworkProtectionOnWinServer Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: anpws

Required: False
Position: Named
Default value: None
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


### -AttackSurfaceReductionOnlyExclusions
Exclude files and paths from Attack Surface Reduction (ASR) rules. Specify the folders or files and resources that should be excluded from ASR rules. Enter a folder path or a fully qualified resource name. For example, ""C:\Windows"" will exclude all files in that directory. ""C:\Windows\App.exe"" will exclude only that specific file in that specific folder.

For more information about excluding files and folders from [ASR rules](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules).

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

### -AttackSurfaceReductionRules_Actions
{{ Fill AttackSurfaceReductionRules_Actions Description }}

```yaml
Type: ASRRuleActionType[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AttackSurfaceReductionRules_Ids
{{ Fill AttackSurfaceReductionRules_Ids Description }}

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

### -CheckForSignaturesBeforeRunningScan
Remove whether to check for new virus and spyware definitions before Windows Defender runs a scan.

```yaml
Type: SwitchParameter
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
{{ Fill CloudBlockLevel Description }}

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

### -CloudExtendedTimeout
{{ Fill CloudExtendedTimeout Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cloudextimeout

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControlledFolderAccessAllowedApplications
{{ Fill ControlledFolderAccessAllowedApplications Description }}

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

### -ControlledFolderAccessProtectedFolders
{{ Fill ControlledFolderAccessProtectedFolders Description }}

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

### -DisableArchiveScanning
Removes whether to scan archive files, such as .zip and .cab files, for malicious and unwanted software.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: darchsc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableAutoExclusions
Remove whether to disable the Automatic Exclusions feature for the server.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: dae

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableBehaviorMonitoring
Removes whether to enable behavior monitoring.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: dbm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableBlockAtFirstSeen
Removes whether to enable block at first seen.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: dbaf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableCatchupFullScan
Removes whether Windows Defender runs catch-up scans for scheduled full scans.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: dcfsc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableCatchupQuickScan
Removes whether Windows Defender runs catch-up scans for scheduled quick scans.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: dcqsc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableCpuThrottleOnIdleScans
Remove whether the CPU will be throttled for scheduled scans while the device is idle.

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

### -DisableDatagramProcessing
{{ Fill DisableDatagramProcessing Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ddtgp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableDnsOverTcpParsing
{{ Fill DisableDnsOverTcpParsing Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ddnstcpp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableDnsParsing
{{ Fill DisableDnsParsing Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ddnsp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableEmailScanning
Remove whether Windows Defender parses the mailbox and mail files, according to their specific format, in order to analyze mail bodies and attachments.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: demsc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableGradualRelease
{{ Fill DisableGradualRelease Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: dgr

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableHttpParsing
{{ Fill DisableHttpParsing Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: dhttpp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableInboundConnectionFiltering
{{ Fill DisableInboundConnectionFiltering Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: dicf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableIntrusionPreventionSystem
Remove whether to configure network protection against exploitation of known vulnerabilities.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: dips

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableIOAVProtection
Remove whether Windows Defender scans all downloaded files and attachments.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: dioavp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisablePrivacyMode
Remove whether to disable privacy mode.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: dpm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableRdpParsing
{{ Fill DisableRdpParsing Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: drdpp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableRealtimeMonitoring
Remove whether to use real-time protection.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: drtm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableRemovableDriveScanning
Remove whether to scan for malicious and unwanted software in removable drives, such as flash drives, during a full scan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: drdsc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableRestorePoint
Remove whether to disable scanning of restore points.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: drp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableScanningMappedNetworkDrivesForFullScan
Remove whether to scan mapped network drives. If you specify a value of $False or do not specify a value, Windows Defender scans mapped network drives.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: dsmndfsc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableScanningNetworkFiles
Remove whether to scan for network files. 

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: dsnf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableScriptScanning
Removes whether to disable the scanning of scripts during malware scans.
If you specify a value of $False or do not specify a value, Windows Defender does not scan scripts.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: dscrptsc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableSshParsing
{{ Fill DisableSshParsing Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: dsshp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableTlsParsing
{{ Fill DisableTlsParsing Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: dtlsp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableControlledFolderAccess
{{ Fill EnableControlledFolderAccess Description }}

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

### -EnableDnsSinkhole
{{ Fill EnableDnsSinkhole Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ednss

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableFileHashComputation
{{ Fill EnableFileHashComputation Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: efhc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableFullScanOnBatteryPower
{{ Fill EnableFullScanOnBatteryPower Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: efsobp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableLowCpuPriority
{{ Fill EnableLowCpuPriority Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: elcp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableNetworkProtection
{{ Fill EnableNetworkProtection Description }}

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

### -EngineUpdatesChannel
{{ Fill EngineUpdatesChannel Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: erelr

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExclusionExtension
Specifies an array of file name extensions, such as obj or lib, to exclude from scheduled, custom, and real-time scanning.
This cmdlet removes the exclusions that you specify.

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

### -ExclusionIpAddress
Specifies an array of IP addresses to exclude from scheduled and real-time scanning.

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
This cmdlet removes the exclusions that you specify.

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
This cmdlet removes exclusions of files opened by the processes that you specify.

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

### -ForceUseProxyOnly
{{ Fill ForceUseProxyOnly Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: fupo

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HighThreatDefaultAction
Indicates that this cmdlet removes the automatic remediation action specified for the high threat alert level.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: htdefac

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LowThreatDefaultAction
Indicates that this cmdlet removes the automatic remediation action specified for the low threat alert level.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ltdefac

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MAPSReporting
Remove membership in Microsoft Active Protection Service.

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

### -MeteredConnectionUpdates
{{ Fill MeteredConnectionUpdates Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: mcupd

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModerateThreatDefaultAction
Indicates that this cmdlet removes the automatic remediation action specified for the moderate threat alert level.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: mtdefac

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PlatformUpdatesChannel
{{ Fill PlatformUpdatesChannel Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: prelr

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyBypass
{{ Fill ProxyBypass Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: proxbps

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyPacUrl
{{ Fill ProxyPacUrl Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ppurl

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyServer
{{ Fill ProxyServer Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: proxsrv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PUAProtection
{{ Fill PUAProtection Description }}

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

### -QuarantinePurgeItemsAfterDelay
Remove specified number of days to keep items in the Quarantine folder.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: qpiad

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RandomizeScheduleTaskTimes
Remove whether to select a random time for the scheduled start and scheduled update for definitions.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: rstt

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RealTimeScanDirection
Remove specified scanning configuration for incoming and outgoing files on NTFS volumes.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: rtsd

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemediationScheduleDay
Remove specified day of the week on which to perform a scheduled full scan in order to complete remediation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: rsd

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemediationScheduleTime
Removes specified time of day, as the number of minutes after midnight, to perform a scheduled scan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: rst

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportingAdditionalActionTimeOut
Remove specified number of minutes before a detection in the additional action state changes to the cleared state.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: raat

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportingCriticalFailureTimeOut
Removes specified the number of minutes before a detection in the critically failed state changes to either the additional action state or the cleared state.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: rcto

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportingNonCriticalTimeOut
Removes specified number of minutes before a detection in the non-critically failed state changes to the cleared state.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: rncto

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScanAvgCPULoadFactor
Removes specified maximum percentage CPU usage for a scan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: saclf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScanOnlyIfIdleEnabled
Removes whether to start scheduled scans only when the computer is not in use.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: soiie

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScanParameters
Removes specified scan type to use during a scheduled scan.

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

### -ScanPurgeItemsAfterDelay
Remove specified number of days to keep items in the scan history folder.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: spiad

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScanScheduleDay
Remove specified the day of the week on which to perform a scheduled scan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: scsd

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScanScheduleQuickScanTime
Removes specified time of day, as the number of minutes after midnight, to perform a scheduled quick scan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: scsqst

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScanScheduleTime
Remove specified time of day, as the number of minutes after midnight, to perform a scheduled scan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: scst

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SchedulerRandomizationTime
{{ Fill SchedulerRandomizationTime Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: srt

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SevereThreatDefaultAction
Indicates that this cmdlet removes the automatic remediation action specified for the severe threat alert level.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: stdefac

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharedSignaturesPath
{{ Fill SharedSignaturesPath Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ssp, SecurityIntelligenceLocation, ssl

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureAuGracePeriod
Remove specified grace period, in minutes, for the definition.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: sigagp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureBlobFileSharesSources
{{ Fill SignatureBlobFileSharesSources Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: sigbfs

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureBlobUpdateInterval
{{ Fill SignatureBlobUpdateInterval Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: sigbui

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureDefinitionUpdateFileSharesSources
Remove specified file-share sources for definition updates.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: sigdufss

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureDisableUpdateOnStartupWithoutEngine
Remove whether to initiate definition updates even if no antimalware engine is present.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: sigduoswo

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureFallbackOrder
Remove specified order in which to contact different definition update sources.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: sfo

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureFirstAuGracePeriod
Removes specified grace period, in minutes, for the definition.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: sigfagp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureScheduleDay
Remove specified day of the week on which to check for definition updates.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: sigsd

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureScheduleTime
Remove specified time of day, as the number of minutes after midnight, to check for definition updates.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: sigst

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignaturesUpdatesChannel
{{ Fill SignaturesUpdatesChannel Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: srelr

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureUpdateCatchupInterval
Remove specified number of days after which Windows Defender requires a catch-up definition update.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: siguci

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureUpdateInterval
Remove specified interval at which to check for definition updates.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: sigui

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubmitSamplesConsent
Remove how Windows Defender checks for user consent for certain samples.

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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThreatIDDefaultAction_Ids
Specifies an array of threat IDs.
This cmdlet removes the default actions for the threat IDs that you specify.

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
Removes whether to disable UI lockdown mode.

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

### -UnknownThreatDefaultAction
Indicates that this cmdlet removes the automatic remediation action specified for the unknown threat alert level.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: unktdefac

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

[Add-MpPreference](./Add-MpPreference.md)

[Get-MpPreference](./Get-MpPreference.md)

[Set-MpPreference](./Set-MpPreference.md)
