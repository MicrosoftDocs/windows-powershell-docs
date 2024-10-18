---
description: The Set-MpPreference cmdlet configures preferences for Windows Defender scans and updates.
external help file: MSFT_MpPreference.cdxml-help.xml
Module Name: Defender
ms.date: 03/27/2024
online version: https://learn.microsoft.com/powershell/module/defender/set-mppreference?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-MpPreference
---

# Set-MpPreference

## SYNOPSIS

Configures preferences for Windows Defender scans and updates.

## SYNTAX

```powershell
Set-MpPreference
 [-AllowDatagramProcessingOnWinServer <Boolean>]
 [-AllowNetworkProtectionDownLevel <Boolean>]
 [-AllowNetworkProtectionOnWinServer <Boolean>]
 [-AllowSwitchToAsyncInspection <Boolean>]
 [-ApplyDisableNetworkScanningToIOAV <Boolean>]
 [-AsJob]
 [-AttackSurfaceReductionOnlyExclusions <String[]>]
 [-AttackSurfaceReductionRules_Actions <ASRRuleActionType[]>]
 [-AttackSurfaceReductionRules_Ids <String[]>]
 [-CheckForSignaturesBeforeRunningScan <Boolean>]
 [-CimSession <CimSession[]>]
 [-CloudBlockLevel <CloudBlockLevelType>]
 [-CloudExtendedTimeout <UInt32>]
 [-ControlledFolderAccessAllowedApplications <String[]>]
 [-ControlledFolderAccessProtectedFolders <String[]>]
 [-DefinitionUpdatesChannel <DefinitionUpdatesChannelType>]
 [-DisableArchiveScanning <Boolean>]
 [-DisableAutoExclusions <Boolean>]
 [-DisableBehaviorMonitoring <Boolean>]
 [-DisableBlockAtFirstSeen <Boolean>]
 [-DisableCacheMaintenance <Boolean>]
 [-DisableCatchupFullScan <Boolean>]
 [-DisableCatchupQuickScan <Boolean>]
 [-DisableCpuThrottleOnIdleScans <Boolean>]
 [-DisableDatagramProcessing <Boolean>]
 [-DisableDnsOverTcpParsing <Boolean>]
 [-DisableDnsParsing <Boolean>]
 [-DisableEmailScanning <Boolean>]
 [-DisableFtpParsing <Boolean>]
 [-DisableGradualRelease <Boolean>]
 [-DisableHttpParsing <Boolean>]
 [-DisableInboundConnectionFiltering <Boolean>]
 [-DisableIOAVProtection <Boolean>]
 [-DisableNetworkProtectionPerfTelemetry <Boolean>]
 [-DisablePrivacyMode <Boolean>]
 [-DisableRdpParsing <Boolean>]
 [-DisableRealtimeMonitoring <Boolean>]
 [-DisableRemovableDriveScanning <Boolean>]
 [-DisableRestorePoint <Boolean>]
 [-DisableScanningMappedNetworkDrivesForFullScan <Boolean>]
 [-DisableScanningNetworkFiles <Boolean>]
 [-DisableScriptScanning <Boolean>]
 [-DisableSmtpParsing <Boolean>]
 [-DisableSshParsing <Boolean>]
 [-DisableTlsParsing <Boolean>]
 [-EnableControlledFolderAccess <ControlledFolderAccessType>]
 [-EnableConvertWarnToBlock <Boolean>]
 [-EnableDnsSinkhole <Boolean>]
 [-EnableFileHashComputation <Boolean>]
 [-EnableFullScanOnBatteryPower <Boolean>]
 [-EnableLowCpuPriority <Boolean>]
 [-EnableNetworkProtection <ASRRuleActionType>]
 [-EnableUdpReceiveOffload <Boolean>]
 [-EnableUdpSegmentationOffload <Boolean>]
 [-EngineUpdatesChannel <UpdatesChannelType>]
 [-ExclusionExtension <String[]>]
 [-ExclusionIpAddress <String[]>]
 [-ExclusionPath <String[]>]
 [-ExclusionProcess <String[]>]
 [-Force]
 [-ForceUseProxyOnly <Boolean>]
 [-HighThreatDefaultAction <ThreatAction>]
 [-IntelTDTEnabled <Boolean>]
 [-LowThreatDefaultAction <ThreatAction>]
 [-MAPSReporting <MAPSReportingType>]
 [-MeteredConnectionUpdates <Boolean>]
 [-ModerateThreatDefaultAction <ThreatAction>]
 [-OobeEnableRtpAndSigUpdate <Boolean>]
 [-PlatformUpdatesChannel <UpdatesChannelType>]
 [-ProxyBypass <String[]>]
 [-ProxyPacUrl <String>]
 [-ProxyServer <String>]
 [-PUAProtection <PUAProtectionType>]
 [-QuarantinePurgeItemsAfterDelay <UInt32>]
 [-RandomizeScheduleTaskTimes <Boolean>]
 [-RealTimeScanDirection <ScanDirection>]
 [-RemediationScheduleDay <Day>]
 [-RemediationScheduleTime <DateTime>]
 [-ReportingAdditionalActionTimeOut <UInt32>]
 [-ReportingCriticalFailureTimeOut <UInt32>]
 [-ReportingNonCriticalTimeOut <UInt32>]
 [-ScanAvgCPULoadFactor <Byte>]
 [-ScanOnlyIfIdleEnabled <Boolean>]
 [-ScanParameters <ScanType>]
 [-ScanPurgeItemsAfterDelay <UInt32>]
 [-ScanScheduleDay <Day>]
 [-ScanScheduleOffset <UInt32>]
 [-ScanScheduleQuickScanTime <DateTime>]
 [-ScanScheduleTime <DateTime>]
 [-SchedulerRandomizationTime <UInt32>]
 [-ServiceHealthReportInterval <UInt32>]
 [-SevereThreatDefaultAction <ThreatAction>]
 [-SharedSignaturesPath <String>]
 [-SignatureAuGracePeriod <UInt32>]
 [-SignatureBlobFileSharesSources <String>]
 [-SignatureBlobUpdateInterval <UInt32>]
 [-SignatureDefinitionUpdateFileSharesSources <String>]
 [-SignatureDisableUpdateOnStartupWithoutEngine <Boolean>]
 [-SignatureFallbackOrder <String>]
 [-SignatureFirstAuGracePeriod <UInt32>]
 [-SignatureScheduleDay <Day>]
 [-SignatureScheduleTime <DateTime>]
 [-SignatureUpdateCatchupInterval <UInt32>]
 [-SignatureUpdateInterval <UInt32>]
 [-SignaturesUpdatesChannel <UpdatesChannelType>]
 [-SubmitSamplesConsent <SubmitSamplesConsentType>]
 [-ThreatIDDefaultAction_Actions <ThreatAction[]>]
 [-ThreatIDDefaultAction_Ids <Int64[]>]
 [-ThrottleLimit <Int32>]
 [-UILockdown <Boolean>]
 [-UnknownThreatDefaultAction <ThreatAction>]
 [<CommonParameters>]
```

## DESCRIPTION

The **Set-MpPreference** cmdlet configures preferences for Windows Defender scans and updates.
You can modify exclusion file name extensions, paths, or processes, and specify the default action
for high, moderate, and low threat levels.

**REMEDIATION VALUES**:

The following table provides remediation action values for detected threats at low, medium, high, and severe alert levels.

|Value|Action|
|---|---|
|0 (NULL)|Apply action based on the Security Intelligence Update (SIU). This is the default value.|
|1|Clean the detected threat.|
|2|Quarantine the detected threat.|
|3|Remove the detected threat.|
|6|Allow the detected threat.|
|8|Allow the user to determine the action to take with the detected threat.|
|9|Don't take any action.|
|10|Block the detected threat.|

## EXAMPLES

### Example 1: Schedule to check for definition updates everyday

```powershell
PS C:\> Set-MpPreference -SignatureScheduleDay Everyday
```

This command configures preferences to check for definition updates every day.

### Example 2: Schedule a time of day to check for definition updates

```powershell
PS C:\> Set-MpPreference -SignatureScheduleTime 02:00:00
```

This command configures preferences to check for definition updates 120 minutes after midnight on days when it's scheduled to check.

## PARAMETERS

### -AllowDatagramProcessingOnWinServer

Specifies whether to disable the inspection of UDP connections on Windows Server. Valid values are:

- $true: The inspection of UDP connections is enabled.
- $false: The inspection of UDP connections is disabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: adpows

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowNetworkProtectionDownLevel

Specifies whether to allow network protection to be set to Enabled or Audit Mode on Windows versions
before 1709. Valid values are:

- $true: Allow network protection to be set to Enabled or Audit Mode on Windows v1709 or earlier.
- $false: Don't allow network protection to be set to Enabled or Audit Mode on Windows v1709 or
earlier.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: anpdl

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowNetworkProtectionOnWinServer

Specifies whether to allow network protection to be set to Enabled or Audit Mode for Windows Server.
Valid values are:

- $true: Allow network protection to be set to Enabled or Audit Mode on Windows Server.
- $false: Don't allow network protection to be set to Enabled or Audit Mode on Windows Server.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: anpws

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowSwitchToAsyncInspection

Specifies whether to enable a performance optimization that allows synchronously inspected network
flows to switch to async inspection once they have been checked and validated. Valid values are:

- $true: Allow synchronously inspected network flows to switch to async inspection once they have
been checked and validated.
- $false: Don't allow synchronously inspected network flows to switch to async inspection once they
have been checked and validated.

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

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

The cmdlet immediately returns an object that represents the job and then displays the command
prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372)
cmdlet.

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

### -AttackSurfaceReductionOnlyExclusions

Specifies the folders or files to exclude from Attack Surface Reduction (ASR) rules. Enter a folder
path or a fully qualified resource name. For example:

- `"C:\Windows"` excludes all files in that folder.
- `"C:\Windows\App.exe"` excludes only that specific file in that specific folder.

To replace all existing values with the values you specify, use the following syntax: `"Value1","Value2",..."ValueN"`.

To add values without affecting existing values, use the **Add-MPPreference** cmdlet:

`Add-MpPreference -AttackSurfaceReductionOnlyExclusions "Value1","Value2",..."ValueN"`

To remove values without affecting other existing values, use the **Remove-MPPreference** cmdlet:

`Remove-MpPreference -AttackSurfaceReductionOnlyExclusions "Value1","Value2",..."ValueN"`

To empty the list, use the value $null for this parameter.

For more information, see [Exclude files and folders from attack surface reduction rules](/defender-endpoint/enable-attack-surface-reduction#exclude-files-and-folders-from-attack-surface-reduction-rules).

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

Use the **AttackSurfaceReductionRules_Ids** and **AttackSurfaceReductionRules_Actions** parameters
together in the same command to specify the states of attack surface reduction (ASR) rules.

- The **AttackSurfaceReductionRules_Ids** parameter identifies the ASR rule by GUID value. For
example, the GUID value of the "Block Office communication application from creating child
processes" ASR rule is `26190899-1602-49e8-8b27-eb1d0a1ce869`. For more information, see
[ASR rule to GUID matrix](/defender-endpoint/attack-surface-reduction-rules-reference#asr-rule-to-guid-matrix).
- The **AttackSurfaceReductionRules_Actions** parameter identifies ASR rule action:

  • 0: Deactivated

  • 1: Activated

  • 2: Audit mode

  • 6: Warning

To replace all existing values with the values you specify, use the following syntax:

`Set-MpPreference -AttackSurfaceReductionRules_Ids Rule1,Rule2,...RuleN -AttackSurfaceReductionRules_Actions Action1,Action2,...ActionN`

To add values without affecting existing values, use the **Add-MPPreference** cmdlet:

`Add-MpPreference -AttackSurfaceReductionRules_Ids Rule1,Rule2,...RuleN -AttackSurfaceReductionRules_Actions Action1,Action2,...ActionN`

To remove values without affecting other existing values, use the **Remove-MPPreference** cmdlet:

`Remove-MpPreference -AttackSurfaceReductionRules_Ids Rule1,Rule2,...RuleN -AttackSurfaceReductionRules_Actions Action1,Action2,...ActionN`

To empty the list, use the value $null for this parameter.

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

Use the **AttackSurfaceReductionRules_Ids** and **AttackSurfaceReductionRules_Actions** parameters
together in the same command to specify the states of attack surface reduction (ASR) rules.

- The **AttackSurfaceReductionRules_Ids** parameter identifies the ASR rule by GUID value. For
example, the GUID value of the "Block Office communication application from creating child
processes" ASR rule is `26190899-1602-49e8-8b27-eb1d0a1ce869`. For more information, see
[ASR rule to GUID matrix](/defender-endpoint/attack-surface-reduction-rules-reference#asr-rule-to-guid-matrix).
- The **AttackSurfaceReductionRules_Actions** parameter identifies ASR rule action for the
- corresponding ASR rule. Valid values are:

  • 0 or Disabled

  • 1 or Enabled

  • 2 or AuditMode

  • 5 or NotConfigured

  • 6 or Warn

To replace all existing values with the values you specify, use the following syntax:

`Set-MpPreference -AttackSurfaceReductionRules_Ids Rule1,Rule2,...RuleN -AttackSurfaceReductionRules_Actions Action1,Action2,...ActionN`

To add values without affecting existing values, use the **Add-MPPreference** cmdlet:

`Add-MpPreference -AttackSurfaceReductionRules_Ids Rule1,Rule2,...RuleN -AttackSurfaceReductionRules_Actions Action1,Action2,...ActionN`

To remove values without affecting other existing values, use the **Remove-MPPreference** cmdlet:

`Remove-MpPreference -AttackSurfaceReductionRules_Ids Rule1,Rule2,...RuleN -AttackSurfaceReductionRules_Actions Action1,Action2,...ActionN`

To empty the list, use the value $null for this parameter.

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

Indicates whether to check for new virus and spyware definitions before Windows Defender runs a
scan. Valid values are:

- $true: Windows Defender checks for new definitions before running a scan.
- $false: The scan begins with the existing definitions. This is the default value.

This parameter applies to scheduled scans, but it has no effect on scans initiated manually from the
user interface from the command line using `mpcmdrun -Scan`.

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

Runs the cmdlet in a remote session or on a remote computer that were created by the
[New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) cmdlet and specified by the
[Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. For example:

`Set-MpPreference -CimSession (Get-CimSession -ID 1),(Get-CimSession -ID 2),...(Get-CimSession -ID N)`

or

`Set-MpPreference -CimSession (Get-CimSession -ID Server1),(Get-CimSession -ID Server2),...(Get-CimSession -ID ServerN)`

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

Specifies the cloud block level that determines how aggressively Microsoft Defender Antivirus scans
and blocks suspicious files. Valid values are:

- 0 or Default
- 1 or Moderate
- 2 or High
- 4 or HighPlus
- 6 or ZeroTolerance

```yaml
Type: CloudBlockLevelType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CloudExtendedTimeout

Specifies the amount of extended time in seconds to block a suspicious file and scan it in the
cloud. Without using this parameter, the standard time is 10 seconds.

Valid values for this parameter are are from 0 to 50 additional seconds.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: cloudextimeout

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControlledFolderAccessAllowedApplications

Specifies the path and filename of applications that are allowed to make changes in controlled
folders. You can use absolute folder paths (for example `C;\Windows\...` or environment variables
(for example, `%appdata%...`) for path names.

To replace all existing values with the values you specify, use the following syntax:
`"PathAndFileName1","PathAndFileName2",..."PathAndFileNameN"`.

To add values without affecting existing values, use the **Add-MPPreference** cmdlet:

`Add-MpPreference -ControlledFolderAccessAllowedApplications "PathAndFileName1","PathAndFileName2",..."PathAndFileNameN"`

To remove values without affecting other existing values, use the **Remove-MPPreference** cmdlet:

`Remove-MpPreference -ControlledFolderAccessAllowedApplications "PathAndFileName1","PathAndFileName2",..."PathAndFileNameN"`

To empty the list, use the value $null for this parameter.

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

Specifies additional folders to protect as controlled access folders. You can use absolute folder
paths (for example `C;\Windows\...` or environment variables (for example, `%appdata%...`) for path
names.

To replace all existing values with the values you specify, use the following syntax:
`"Path1","Path2"..."PathN"`.

To add values without affecting existing values, use the **Add-MPPreference** cmdlet:

`Add-MpPreference -ControlledFolderAccessAllowedApplications "Path1","Path2",..."PathN"`

To remove values without affecting other existing values, use the **Remove-MPPreference** cmdlet:

`Remove-MpPreference -ControlledFolderAccessAllowedApplications "Path1","Path2",..."PathN"`

To empty the list, use the value $null for this parameter.

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

### -DefinitionUpdatesChannel

Specifies when devices receive daily Microsoft Defender definition updates during the monthly gradual
rollout. Valid values are:

- NotConfigured: Devices stay up to date automatically during the gradual release cycle. This value
is suitable for most devices.
- Staged: Devices are offered updates after the monthly gradual release cycle. This value is
suggested for a small, representative part of your production population, around 10 percent.
- Broad: Devices are offered updates only after the gradual release cycle completes. This value is
suggested for a broad set of devices in your production population, from 10 to 100 percent.

This parameter replaces the **SignaturesUpdatesChannel** parameter.

```yaml
Type: DefinitionUpdatesChannelType
Parameter Sets: (All)
Aliases: duc
Accepted values: NotConfigured, Staged, Broad

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableArchiveScanning

Indicates whether to scan archive files, such as .zip and .cab files, for malicious and unwanted
software. Valid values are:

- $true: Windows Defender doesn't scan archive file.
- $false: Windows Defender scans archive files. This is the default value.

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

Indicates whether to disable the Automatic Exclusions feature for the server. Valid values are:

- $true: Windows Defender disables the Automatic Exclusions feature for the server.
- $false: Windows Defender enables the Automatic Exclusions feature for the server. This is the default value.

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

Indicates whether to enable behavior monitoring. Valid values are:

- $true: Windows Defender disables behavior monitoring.
- $false: Windows Defender enables behavior monitoring. This is the default value.

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

Indicates whether to enable block at first seen. Valid values are:

- $true: Windows Defender disables block at first seen.
- $false: Windows Defender enables block at first seen. This is the default value.

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

### -DisableCacheMaintenance

Defines whether the cache maintenance idle task performs cache maintenance. Valid values are:

- $true: Cache maintenance is disabled.
- $false: Cache maintenance is enabled. This is the default value.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dcm

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableCatchupFullScan

Indicates whether Windows Defender runs catch-up scans for missed scheduled full scans. Valid values
are:

- $true: Windows Defender doesn't run catch-up scans for missed scheduled full scans.
- $false: After two missed scheduled full scans, Windows Defender runs a catch-up scan.
the next time someone signs in to the computer.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dcfsc

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableCatchupQuickScan

Indicates whether Windows Defender runs catch-up scans for missed scheduled quick scans. Valid values
are:

$true: Windows Defender doesn't run catch-up scans for missed scheduled quick scans.
$false: After two missed scheduled quick scans, Windows Defender runs a catch-up scan
the next time someone signs in to the computer.

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

Indicates whether the CPU is throttled for scheduled scans while the device is idle. Valid
values are:

- $true: The CPU is throttled for scheduled scans.
- $false: The CPU isn't throttled for scheduled scans, regardless of the value of the
**ScanAvgCPULoadFactor** parameter.

This parameter doesn't affect other types scheduled scans. Normal CPU throttling occurs on other types of scheduled scans.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: None
Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableDatagramProcessing

Specifies whether to disable inspection of UDP connections. Valid values are:

- $true: Inspection of UDP connections is disabled.
- $false: Inspection of UDP connections is enabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: ddtgp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableDnsOverTcpParsing

Specifies whether to disable inspection of DNS traffic that occurs over a TCP. Valid values
are:

- $true: Inspection of DNS traffic over TCP is disabled.
- $false: Inspection of DNS traffic over TCP is enabled.

Network protection needs to inspect DNS traffic over TCP in the following scenarios:

- To provide metadata for anti-malware behavior monitoring.
- To allow for a DNS sinkhole if the **EnableDnsSinkhole** parameter is set to the value $true.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: ddnstcpp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableDnsParsing

Specifies whether to disable inspection of DNS traffic that occurs over a UDP. Valid values
are:

- $true: Inspection of DNS traffic over UDP is disabled.
- $false: Inspection of DNS traffic over UDP channels is enabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: ddnsp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableFtpParsing

Specifies whether to disable FTP parsing for network protection. Valid values are:

- $true: FTP parsing for network protection is disabled.
- $false: FTP parsing for network protection is enabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dfp

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableEmailScanning

Indicates whether Windows Defender parses mailbox and email message files to analyze message bodies
and email attachments. Valid values are:

- $true: Windows Defender doesn't scan mailbox and email message files.
- $false: Windows Defender scans mailbox and email message files. This is the default value.

 Windows Defender supports several mailbox and email message file formats. For example:

- .binhex
- .dbx
- .mbx
- .mime
- .pst

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

Specifies whether to disable gradual rollout of monthly and daily Windows Defender updates. Valid
values are:

- $true: Devices are offered all updates after the gradual release cycle finishes. Consider this
option for datacenter computers that receive only limited updates.
- $false: This is the default value. Devices remain in the Current Channel unless otherwise
specified in specific channels. The device stays up to date automatically during the gradual release
cycle, which is suitable for most devices.

This setting applies to both monthly and daily updates. This setting overrides configured channel
selections for platform and engine updates.

This policy is available starting with platform version 4.18.2106.5 and later.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dgr

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableHttpParsing

Specifies whether to disable inspection of HTTP traffic. Valid values are:

- $true: Inspection of HTTP traffic is disabled.
- $false: Inspection of HTTP traffic is enabled.

If the value of the **EnableNetworkProtection** parameter is `Enabled`, HTTP connections to
malicious websites can be blocked.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dhttpp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableInboundConnectionFiltering

Specifies whether Network Protection inspects only outbound connections. Valid values are:

- $true: Network Protection inspects only outbound connections.
- $false: Network Protection inspects inbound and outbound connections. This is the default value.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dicf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableIOAVProtection

Indicates whether Windows Defender scans all downloaded files and attachments. Valid values are:

- $true: Windows Defender doesn't scan all downloaded files and attachments.
- $false: Windows Defender scans all downloaded files and attachments. This is the default value.

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

### -DisableNetworkProtectionPerfTelemetry

This setting disables the gathering and sending of performance telemetry from network protection.
Valid values are:

- $true: Network protection telemetry is disabled.
- $false: Network protection telemetry is enabled. This is the default value.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dnpp

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisablePrivacyMode

**Note**: This parameter is a legacy setting that doesn't affect current platforms.

The intent of this parameter was to disable privacy mode, which prevented users (not admins) from
displaying the threat history.

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

### -DisableRdpParsing

This setting controls whether to parse RDP traffic to look for malicious attacks using the RDP
protocol. Valid values are:

- $true: Windows Defender doesn't scan RDP traffic.
- $false: Windows Defender scans RDP traffic.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: drdpp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableRealtimeMonitoring

Indicates whether to use real-time protection. Valid values are:

- $true: Windows Defender doesn't use real-time protection.
- $false: Windows Defender uses real-time protection. This is the default and recommended value.

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

Indicates whether to scan for malicious and unwanted software in removable drives, such as flash
drives, during a full scan. Valid values are:

- $true: Windows Defender doesn't scan removable drives during a full scan, but can still scan
removable drives during quick scans or custom scans.
- $false: Windows Defender scans removable drives during any type of scan. This is the default
value.

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

Indicates whether to disable scanning of restore points. Valid values are:

- $true: Windows Defender restore point scanning is disabled.
- $false: Windows Defender restore point scanning is enabled. This is the default value.

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

Indicates whether to scan mapped network drives. Valid values are:

- $true: Windows Defender doesn't scan mapped network drives.
- $false: Windows Defender scans mapped network drives. This is the default value.

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

Indicates whether to scan network files. Valid values are:

- $true: Windows Defender doesn't scan network files.
- $false: Windows Defender scans network files. This is the default value.

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

Specifies whether to disable the scanning of scripts during malware scans. Valid values are:

- $true: Windows Defender doesn't scan scripts.
- $false: Windows Defender scans scripts. This is the default value.

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

### -DisableSshParsing

Specifies whether to disable the inspection of SSH traffic. Valid values are:

- $true: Network Protection doesn't inspect SSH traffic.
- $false: Network Protection inspects SSH traffic. This is the default value.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dsshp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableSmtpParsing

This setting disables SMTP parsing by Network Protection. Valid values are:

- $true: SMTP parsing is disabled.
- $false: SMTP parsing is enabled. This is the default value

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dsp

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableTlsParsing

Specifies whether to disable the inspection of TLS traffic. Valid values are:

- $true: Network Protection doesn't inspect TLS traffic.
- $false: Network Protection inspects TLS traffic. This is the default value.

Network protection inspects TLS traffic (also known as HTTPS traffic) to see if a connection is
being made to a malicious website, and to provide metadata to behavior monitoring.

TLS connections to malicious websites can also be blocked if the value of the
**EnableNetworkProtection** parameter is `Enabled`.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: dtlsp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableControlledFolderAccess

<!--- Regardless of the value I enter, the property value in Get-MpPreference is 3--->

Specifies the state for the controlled folder access feature. Valid values are:

- Disabled
- Enabled
- AuditMode
- BlockDiskModificationOnly
- AuditDiskModificationOnly

```yaml
Type: ControlledFolderAccessType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableConvertWarnToBlock

This setting controls whether network protection blocks network traffic instead of displaying a
warning. Valid values are:

- $true: Network Protection blocks network traffic instead of displaying a warning.
- $false: Network Protection displaying a warning.

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

### -EnableDnsSinkhole

Specifies whether to examine DNS traffic to detect and sinkhole DNS exfiltration attempts and other
DNS based malicious attacks. Valid values are:

- $true: DNS sinkhole is enabled. Network protection can inspect the DNS traffic of a machine and,
in conjunction with behavior monitoring, detect and sinkhole DNS exfiltration attempts, and other
DNS based malicious attacks.
- $false: DNS sinkhole is disabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: ednss

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableFileHashComputation

Specifies whether to enable file hash computation. Valid values are:

- $true: Windows Defender computes hashes for scanned files.
- $false: Windows Defender doesn't compute hashes for scanned files.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: efhc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableFullScanOnBatteryPower

Specifies whether Windows Defender does full scans while on battery power. Valid values are:

- $true: Windows Defender does full scans while on battery power.
- $false: Windows Defender doesn't do full scans while on battery power.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: efsobp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableLowCpuPriority

Specifies whether Windows Defender uses low CPU priority for scheduled scans. Valid values are:

- $true: Windows Defender uses low CPU priority for scheduled scans.
- $false: Windows Defender doesn't use low CPU priority for scheduled scans.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: elcp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableNetworkProtection

<!--- Regardless of the value I enter, the property value in Get-MpPreference is always 1--->

Specifies how the network protection service handles web-based malicious threats, including phishing
and malware. Valid values are:

- Disabled
- Enabled
- AuditMode
- NotConfigured
- Warn

```yaml
Type: ASRRuleActionType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableUdpReceiveOffload

Specifies whether UDP receive offload support in Network Protection is enabled, resulting in
potentially higher inbound UDP bandwidth. Valid values are:

- $true: UDP receive offload support in Network Protection is enabled.
- $false: UDP receive offload support in Network Protection is disabled.

Starting with platform version `4.18.24030`, Microsoft will gradually move the default value from
disabled to enabled.

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

### -EnableUdpSegmentationOffload

Specifies whether UDP segmentation offload support in Network Protection is enabled, resulting in
potentially higher outbound UDP bandwidth in the outbound direction. Valid values are:

- $true: UDP segmentation offload support in Network Protection is enabled.
- $false: UDP segmentation offload support in Network Protection is disabled.

Starting with platform version `4.18.24030`, Microsoft will gradually move the default value from
disabled to enabled.

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

### -EngineUpdatesChannel

Specifies when devices receive Microsoft Defender engine updates during the monthly gradual
rollout. Valid values are:

- 0 or NotConfigured: Devices stay up to date automatically during the gradual release cycle. This
value is suitable for most devices.
- 2 or Beta: Devices are the first to receive new updates. Select Beta Channel to participate in
identifying and reporting issues to Microsoft. Devices in the Windows Insider Program are
subscribed to this channel by default. This value is for use in manual test environments only and a
limited number of devices.
- 3 or Preview: Devices are offered updates earliest during the monthly gradual release cycle. This
value is suggested for pre-production or validation environments.
- 4 or Staged: Devices are offered updates after the monthly gradual release cycle. This value is
suggested for a small, representative part of your production population, around 10 percent.
- 5 or Broad: Devices are offered updates only after the gradual release cycle completes. This
value is suggested for a broad set of devices in your production population, from 10 to 100 percent.
- 6 or Delayed

```yaml
Type: UpdatesChannelType
Parameter Sets: (All)
Aliases: euc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExclusionExtension

Specifies the file name extensions, such as `obj` and `lib`, to exclude from scheduled, custom,
and real-time scanning.

To replace all existing values with the values you specify, use the following syntax: `"Extension1","Extension2",..."ExtensionN"`.

To add values without affecting existing values, use the **Add-MPPreference** cmdlet:

`Add-MpPreference -ExclusionExtension "Extension1","Extension2"..."ExtensionN"`

To remove values without affecting other existing values, use the **Remove-MPPreference** cmdlet:

`Remove-MpPreference -ExclusionExtension "Extension1","Extension2"..."ExtensionN"`

To empty the list, use the value $null for this parameter.

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

Specifies the IP addresses to exclude from scheduled and real-time scanning.

To replace all existing values with the values you specify, use the following syntax: `"IPAddress1","IPAddress2",..."IPAddresseN"`.

To add values without affecting existing values, use the **Add-MPPreference** cmdlet:

`Add-MpPreference -ExclusionIpAddress "IPAddress1","IPAddress",..."IPAddressN"`

To remove values without affecting other existing values, use the **Remove-MPPreference** cmdlet:

`Remove-MpPreference -ExclusionIpAddress "IPAddress1","IPAddress2",..."IPAddressN"`

To empty the list, use the value $null for this parameter.

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

Specifies the path and filename (for specific files) or path only (for all files in the folder) to
exclude from scheduled and real-time scanning.

To replace all existing values with the values you specify, use the following syntax:
`"Value1","Value2"..."ValueN"`.

To add values without affecting existing values, use the **Add-MPPreference** cmdlet:

`Add-MpPreference -ExclusionPath "Value1","Value2",..."ValuehN"`

To remove values without affecting other existing values, use the **Remove-MPPreference** cmdlet:

`Remove-MpPreference -ExclusionPath "Value1","Value2",..."ValueN"`

To empty the list, use the value $null for this parameter.

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

Specifies the paths to process images to exclude from scheduled and real-time scanning.

To replace all existing values with the values you specify, use the following syntax:
`"Path1","Path2"..."PathN"`.

To add values without affecting existing values, use the **Add-MPPreference** cmdlet:

`Add-MpPreference -ExclusionProcess "Path1","Path2",..."PathhN"`

To remove values without affecting other existing values, use the **Remove-MPPreference** cmdlet:

`Remove-MpPreference -ExclusionProcess "Path1","Path2",..."PathN"`

To empty the list, use the value $null for this parameter.

This parameter excludes files opened by executable programs only, not the processes themselves.
To exclude processes, use the **ExclusionPath** parameter.

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

Forces the command to run without asking for user confirmation. You don't need to specify a value
with this switch.

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

Specifies whether to force the device to use only the proxy. Valid values are:

- $true: Use the proxy only.
- $false: Don't force the device to use the proxy.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: fupo

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HighThreatDefaultAction

<!--- Regardless of the value I enter, the property value in Get-MpPreference is 0--->

Specifies the automatic remediation action to take for a high level threat. Valid values are:

- Clean
- Quarantine
- Remove
- Allow
- UserDefined
- NoAction
- Block

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

### -IntelTDTEnabled

This policy setting configures the Intel TDT integration level for Intel TDT-capable devices. Valid
values are:

- $true: Intel TDT integration is turned on.
- $false: Intel TDT integration is turned off.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: itdte
Accepted values: 0,1 and 2

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -LowThreatDefaultAction

<!--- Regardless of the value I enter, the property value in Get-MpPreference is 0--->

Specifies the automatic remediation action to take for a low level threat. Valid values are:

- Clean
- Quarantine
- Remove
- Allow
- UserDefined
- NoAction
- Block

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

<!--- Regardless of the value I enter, the property value in Get-MpPreference is 2--->

Specifies the type of membership in Microsoft Active Protection Service. This services is an online
community that helps you choose how to respond to potential threats. The community also helps
prevent the spread of new malicious software. Valid values are:

- Disabled: Send no information to Microsoft. This is the default value.
- Basic: Send basic information to Microsoft about detected software, including where the software
came from, the actions you applied (manually or automatically), and whether the actions succeeded.
- Advanced: In addition to basic information, send more information to Microsoft about malicious
software, spyware, and potentially unwanted software, including the location of the software,
filenames, how the software operates, and how it affects your computer.

If you join this community, you can choose to automatically send basic or additional information
about detected software. Additional information helps Microsoft create new definitions. In some
instances, personal information might unintentionally be sent to Microsoft. However, Microsoft
doesn't use this information to identify you or contact you.

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

### -MeteredConnectionUpdates

Specifies whether to update managed devices to update through metered connections. Valid values are:

- $true: Updates are made over metered connections. Data charges may apply.
- $false: Updates aren't made over metered connections.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: mcupd

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModerateThreatDefaultAction

<!--- Regardless of the value I enter, the property value in Get-MpPreference is 0--->

Specifies the automatic remediation action to take for a moderate level threat. Valid values are:

- Clean
- Quarantine
- Remove
- Allow
- UserDefined
- NoAction
- Block

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

### -OobeEnableRtpAndSigUpdate

This setting allows you to configure whether real-time protection and Security Intelligence Updates
are enabled during Out of Box experience (OOBE). Valid values are:

- $true: Real-time protection and Security Intelligence Updates are enabled during OOBE.
- $false: Real-time protection and Security Intelligence Updates during OOBE aren't enabled. This
is the default value.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PlatformUpdatesChannel

Specifies when devices receive Microsoft Defender platform updates during the monthly gradual
rollout. Valid values are:

- NotConfigured: Devices stay up to date automatically during the gradual release cycle. This value
is suitable for most devices.
- Beta: Devices are the first to receive new updates. Select Beta Channel to participate in
identifying and reporting issues to Microsoft. Devices in the Windows Insider Program are
subscribed to this channel by default. This value is for use in manual test environments only and
for a limited number of devices.
- Preview: Devices are offered updates earliest during the monthly gradual release cycle. This value
is suggested for pre-production or validation environments.
- Staged: Devices are offered updates after the monthly gradual release cycle. This value is
suggested for a small, representative part of your production population, around 10 percent.
- Broad: Devices are offered updates only after the gradual release cycle completes. This value is
suggested for a broad set of devices in your production population, from 10 to 100 percent.
- Delayed

```yaml
Type: UpdatesChannelType
Parameter Sets: (All)
Aliases: prelr

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyBypass

Specifies proxy bypasses.

To replace all existing values with the values you specify, use the following syntax: `"Value1","Value2",..."ValueN"`.

To add values without affecting existing values, use the following syntax:

`$a = Get-MpPreference | Select-Object -Expand ProxyBypass`

`$ += "Value1","Value2"..."ValueN"`

`Set-MpPreference -ProxyBypass $a`

To remove values without affecting existing values, do the following steps:

- Run the following commands to see the existing list of values in order:

  `$x = Get-MpPreference`

  `$r = [System.Collections.ArrayList]($x.ProxyBypass)`

  `$r`

   The first value in the list has the index number 0, the second has the index number 1, and so on.

- Use the index number to specify the value to remove. For example, to remove the seventh value in
the list, run the following commands:

  `$r.RemoveAt(6)`

  `Set-MpPreference -ProxyBypass $r`

To empty the list, use the value $null for this parameter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: proxbps

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyPacUrl

Specifies the Privilege Attribute Certificate (PAC) proxy.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ppurl

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyServer

Specifies the proxy server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: proxsrv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PUAProtection

<!--- Regardless of the value I enter, the property value in Get-MpPreference is 1--->

Specifies the level of detection for potentially unwanted applications. Valid values are:

- Disabled
- Enabled: You're warned when potentially unwanted software is downloaded or attempts to install
itself on your computer.
- Audit

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

### -QuarantinePurgeItemsAfterDelay

<!--- Regardless of the value I enter, the property value in Get-MpPreference is 15--->

Specifies the number of days to keep items in the Quarantine folder.

No value or the value 0 means items stay in the Quarantine folder indefinitely.

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

Indicates whether to select a random time for the scheduled start and scheduled update for
definitions. Valid values are:

- $true: Scheduled tasks begin within 30 minutes before or after the scheduled time. This is the
default value.
- $false: Scheduled tasks begin on the scheduled time

Randomized start times can distribute the impact of scanning. For example, if several virtual
machines share the same host, randomized start times prevent all the hosts from starting the
scheduled tasks at the same time.

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

Specify a value for this parameter to enhance performance on servers which have a large number of file transfers, but need scanning for either incoming or outgoing files.
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
If you specify a value of 8 or do not specify a value, Windows Defender performs a scheduled full scan to complete remediation by using a default frequency.

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
If you do not specify a value for this parameter, a scheduled scan runs at the default time of two hours after midnight.

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
Windows Defender does not exceed the percentage of CPU usage that you specify.
The default value is 50.

Note: This is not a hard limit but rather a guidance for the scanning engine to not exceed this maximum on average. If ScanOnlyIfIdleEnabled (instructing the product to scan only when the computer is not in use) and DisableCpuThrottleOnIdleScans (instructing the product to disable CPU throttling on idle scans) are both enabled, then the value of ScanAvgCPULoadFactor is ignored.

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

Indicates whether to start scheduled scans only when the computer is not in use.
If you specify a value of $True or do not specify a value, Windows Defender runs schedules scans when the computer is on, but not in use.

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

If you do not specify this parameter, Windows Defender uses the default value of quick scan.

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
If you specify a value of zero, Windows Defender does not remove items.
If you do not specify a value, Windows Defender removes items from the scan history folder after the default length of time, which is 15 days.

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
If you specify a value of 8 or do not specify a value, Windows Defender does not perform scheduled scans.

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
If you do not specify a value for this parameter, a scheduled quick scan runs at the time specified by the **ScanScheduleOffset** parameter.
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
Aliases: scso
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

### -SchedulerRandomizationTime

Specifies the randomization time for the scheduler.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: srt

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceHealthReportInterval

This policy setting configures the time interval (in minutes) for the service health reports to be sent from endpoints. These are for Microsoft Defender Antivirus events 1150 and 1151. For more information, see [Microsoft Defender Antivirus event IDs](/microsoft-365/security/defender-endpoint/troubleshoot-microsoft-defender-antivirus#microsoft-defender-antivirus-event-ids).

If you do not configure this setting, the default value will be applied. The default value is set at 60 minutes (one hour).
If you configure this setting to 0, no service health reports will be sent.
The maximum value allowed to be set is 14400 minutes (ten days).

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

### -SharedSignaturesPath

Specifies the shared signatures path.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ssp, SecurityIntelligenceLocation, ssl

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

### -SignatureBlobFileSharesSources

Specifies the file shares sources for signatures.

```yaml
Type: String
Parameter Sets: (All)
Aliases: sigbfs

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureBlobUpdateInterval

Specifies the signature update interval.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: sigbui

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureDefinitionUpdateFileSharesSources

Specifies file-share sources for definition updates.
Specify sources as a bracketed sequence of Universal Naming Convention (UNC) locations, separated by the pipeline symbol; for example, { \\\\Server01\Share01 | \\\\Server02\Share02 | \\\\Server03\Share03}.
If you specify a value for this parameter, Windows Defender attempts to connect to the shares in the order that you specify.
After Windows Defender updates a definition, it stops attempting to connect to shares on the list.
If you do not specify a value for this parameter, the list is empty.

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
If you specify a value of $True or do not specify a value, Windows Defender does not initiate definition updates on startup.
If you specify a value of $False, and if no antimalware engine is present, Windows Defender initiates definition updates on startup.

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
Specify the types of update sources in the order in which you want Windows Defender to contact them, enclosed in braces and separated by the pipeline symbol; for example, { InternalDefinitionUpdateServer | MicrosoftUpdateServer | MMPC }.
The values that you can specify in the string are:

- InternalDefinitionUpdateServer
- MicrosoftUpdateServer
- MMPC
- FileShares

MMPC refers to Microsoft Malware Protection Center.

If you specify a value for this parameter, Windows Defender contacts the definition update sources in the specified order.
After Windows Defender downloads definition updates from a source, it stops attempting to connect to other sources.
If you do not specify a value for this parameter, Windows Defender contacts sources in the default order of { MicrosoftUpdateServer | MMPC }.

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
If you specify a value of 8 or do not specify a value, Windows Defender checks for definition updates by using a default frequency.

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
If you do not specify a value for this parameter, Windows Defender checks for definition updates at the default time of 15 minutes before the scheduled scan time.

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

### -SignaturesUpdatesChannel

This parameter has been replaced by the **DefinitionUpdatesChannel** parameter.

```yaml
Type: UpdatesChannelType
Parameter Sets: (All)
Aliases: srelr

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureUpdateCatchupInterval

Specifies the number of days after which Windows Defender requires a catch-up definition update.
If you do not specify a value for this parameter, Windows Defender requires a catch-up definition update after the default value of one day.

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
If you do not specify a value for this parameter, Windows Defender checks at the default interval.
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
Otherwise, if the **MAPSReporting** parameter does not have a value of Disabled, Windows Defender prompts the user for consent.
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

> [!NOTE]
> A value of 0 (NULL) applies an action based on the Security Intelligence Update (SIU). This is the default value.

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

### -ThrottleForScheduledScanOnly

A CPU usage limit can be applied to scheduled scans only, or to scheduled and custom scans. The default value applies a CPU usage limit to scheduled scans only.
The acceptable values for this parameter are:

- 1 (Default) - If you enable this setting, CPU throttling will apply only to scheduled scans.
- 0 - If you disable this setting, CPU throttling will apply to scheduled and custom scans.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### -UILockdown

Indicates whether to disable UI lockdown mode.
If you specify a value of $True, Windows Defender disables UI lockdown mode.
If you specify $False or do not specify a value, UI lockdown mode is enabled.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-MpPreference](./Add-MpPreference.md)

[Get-MpPreference](./Get-MpPreference.md)

[Remove-MpPreference](./Remove-MpPreference.md)
