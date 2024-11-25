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

> [!NOTE]
> You need to run this cmdlet in an elevated PowerShell window (a PowerShell window you opened by
selecting **Run as administrator**).

## SYNTAX

```powershell
Set-MpPreference
 [-AllowDatagramProcessingOnWinServer <Boolean>]
 [-AllowNetworkProtectionDownLevel <Boolean>]
 [-AllowNetworkProtectionOnWinServer <Boolean>]
 [-AllowSwitchToAsyncInspection <Boolean>]
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
 [-SubmitSamplesConsent <SubmitSamplesConsentType>]
 [-ThreatIDDefaultAction_Actions <ThreatAction[]>]
 [-ThreatIDDefaultAction_Ids <Int64[]>]
 [-ThrottleForScheduledScanOnly <Boolean>]
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

The following table provides remediation action values for detected threats at low, medium, high,
and severe alert levels.

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

This command configures preferences to check for definition updates 120 minutes after midnight on
days when it's scheduled to check.

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

Specifies whether network protection on Windows Server 2016 or Windows Server 2012 R2 is controlled
by the **EnableNetworkProtection** parameter. Valid values are:

- $true: Network protection is controlled by the **EnableNetworkProtection**
parameter (Enabled, Disabled, or AuditMode).

  **Tip**: For Windows Server 2016 or Windows Server 2012 R2, you also need to set the
**AllowNetworkProtectionOnWinServer** parameter to the value $true.

- $false: Network protection isn't controlled by the **EnableNetworkProtection**
parameter.

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

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

Specifies whether network protection on Windows Server is controlled by the
**EnableNetworkProtection** parameter. Valid values are:

- $true: Network protection is controlled by the **EnableNetworkProtection**
parameter (Enabled, Disabled, or AuditMode).

  **Tip**: For Windows Server 2016 or Windows Server 2012 R2, you also need to set the
**AllowNetworkProtectionDownLevel** parameter to the value $true.

- $false: Network protection isn't controlled by the **EnableNetworkProtection**
parameter.

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

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
- The **AttackSurfaceReductionRules_Actions** parameter identifies ASR rule action. Valid values
are:

  • 0 or Deactivated

  • 1 or Activated

  • 2 or Audit mode

  • 6 or Warning

To replace all existing values with the values you specify, use the following syntax:

`Set-MpPreference -AttackSurfaceReductionRules_Ids Rule1,Rule2,...RuleN -AttackSurfaceReductionRules_Actions Action1,Action2,...ActionN`

To add values without affecting existing values, use the **Add-MPPreference** cmdlet:

`Add-MpPreference -AttackSurfaceReductionRules_Ids Rule1,Rule2,...RuleN -AttackSurfaceReductionRules_Actions Action1,Action2,...ActionN`

To remove values without affecting other existing values, use the **Remove-MPPreference** cmdlet:

`Remove-MpPreference -AttackSurfaceReductionRules_Ids Rule1,Rule2,...RuleN -AttackSurfaceReductionRules_Actions Action1,Action2,...ActionN`

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

Specifies whether to check for new virus and spyware definitions before Windows Defender runs a
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

<!---The default value on 2 Win 11 PCs is 0; Max value claimed to be 50 --->

Specifies the amount of extended time in seconds to block a suspicious file and scan it in the
cloud. A valid value is an integer from 0 to 4294967295. The default value is 10 seconds.

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

The value parameter is meaningful only if the value of the **EnableControlledFolderAccess**
parameter isn't `Disabled`.

To specify additional folders that are protected by controlled folder access, use the
**ControlledFolderAccessProtectedFolders** parameter.

For more information about controlled folder access, see [Protect important folders with controlled
folder access](/defender-endpoint/controlled-folders).

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

The value parameter is meaningful only if the value of the **EnableControlledFolderAccess**
parameter isn't `Disabled`.

To specify applications that are allowed to access controlled folders, use the
**ControlledFolderAccessAllowedApplications** parameter.

For more information about controlled folder access, see [Protect important folders with controlled
folder access](/defender-endpoint/controlled-folders).

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

Specifies whether to scan archive files (for example, .zip and .cab files) for malicious and
unwanted software. Valid values are:

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

Specifies whether to disable the Automatic Exclusions feature for the server. Valid values are:

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

Specifies whether to enable behavior monitoring. Valid values are:

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

Specifies whether to enable block at first seen. Valid values are:

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

Specifies whether Windows Defender runs catch-up scans for missed scheduled full scans. Valid values
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

Specifies whether Windows Defender runs catch-up scans for missed scheduled quick scans. Valid values
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

Specifies whether the CPU is throttled for scheduled scans while the device is idle. Valid
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

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

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

### -DisableEmailScanning

Specifies whether Windows Defender parses mailbox and email message files to analyze message bodies
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

### -DisableFtpParsing

Specifies whether to disable FTP parsing for network protection. Valid values are:

- $true: FTP parsing for network protection is disabled.
- $false: FTP parsing for network protection is enabled.

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

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

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

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

Specifies whether Windows Defender scans all downloaded files and attachments. Valid values are:

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

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

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

Specifies whether to use real-time protection. Valid values are:

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

Specifies whether to scan for malicious and unwanted software in removable drives, such as flash
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

Specifies whether to disable scanning of restore points. Valid values are:

- $true: Windows Defender restore point scanning is disabled.
- $false: Windows Defender restore point scanning is enabled. This is the default value.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: drp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableScanningMappedNetworkDrivesForFullScan

Specifies whether to scan mapped network drives. Valid values are:

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

Specifies whether to scan network files. Valid values are:

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

### -DisableSmtpParsing

This setting disables SMTP parsing by network protection. Valid values are:

- $true: SMTP parsing is disabled.
- $false: SMTP parsing is enabled. This is the default value

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

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

### -DisableSshParsing

Specifies whether to disable the inspection of SSH traffic. Valid values are:

- $true: Network protection doesn't inspect SSH traffic.
- $false: Network protection inspects SSH traffic. This is the default value.

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

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

### -DisableTlsParsing

Specifies whether to disable the inspection of TLS traffic. Valid values are:

- $true: Network Protection doesn't inspect TLS traffic.
- $false: Network Protection inspects TLS traffic. This is the default value.

Network protection inspects TLS traffic (also known as HTTPS traffic) to see if a connection is
being made to a malicious website, and to provide metadata to behavior monitoring.

TLS connections to malicious websites can also be blocked if the value of the
**EnableNetworkProtection** parameter is `Enabled`.

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

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

To specify additional folders that are protected by controlled folder access, use the
**ControlledFolderAccessProtectedFolders** parameter.

To specify applications that are allowed to access controlled folders, use the
**ControlledFolderAccessAllowedApplications** parameter.

For more information about controlled folder access, see [Protect important folders with controlled
folder access](/defender-endpoint/controlled-folders).

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

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

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

**Note**: This parameter has been deprecated.

Specifies whether to examine DNS traffic to detect and sinkhole DNS exfiltration attempts and other
DNS based malicious attacks. Valid values are:

- $true: DNS sinkhole is enabled. Network protection can inspect the DNS traffic of a machine and,
in conjunction with behavior monitoring, detect and sinkhole DNS exfiltration attempts, and other
DNS based malicious attacks.
- $false: DNS sinkhole is disabled.

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

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

Specifies how the network protection service handles web-based malicious threats, including phishing
and malware. Valid values are:

- 0 or Disabled
- 1 or Enabled
- 2 or AuditMode

**Tip**: Network protection on Windows Server also requires that the
**AllowNetworkProtectionOnWinServer** and (for Windows Server 2016 or Windows Server 2012 R2)
**AllowNetworkProtectionDownLevel** parameters are set to the value $true.

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

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

Starting with platform version `4.18.24030`, we're gradually moving the default value from
$false (disabled) to $true (enabled).

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

<!--- Regardless of the value I enter, the property value in Get-MpPreference is 0. If I could
change it like UnknownThreatDefaultAction, I wouldn't be able to change it back.--->

Specifies the automatic remediation action to take for high level threats. Valid values are:

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

<!--- Regardless of the value I enter, the property value in Get-MpPreference is 0. If I could
change it like UnknownThreatDefaultAction, I wouldn't be able to change it back.--->

Specifies the automatic remediation action to take for low level threats. Valid values are:

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

Specifies the type of membership in Microsoft Active Protection Service. This services is an online
community that helps you choose how to respond to potential threats. The community also helps
prevent the spread of new malicious software. Valid values are:

- 0 or Disabled: Send no information to Microsoft. This is the default value.
- 1 or Basic: Send basic information to Microsoft about detected software, including where the software
came from, the actions you applied (manually or automatically), and whether the actions succeeded.
- 2 or Advanced: In addition to basic information, send more information to Microsoft about malicious
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

<!--- Regardless of the value I enter, the property value in Get-MpPreference is 0. If I could
change it like UnknownThreatDefaultAction, I wouldn't be able to change it back.--->

Specifies the automatic remediation action to take for moderate level threats. Valid values are:

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

Specifies the level of detection for potentially unwanted applications. Valid values are:

- 0 or Disabled
- 1 or Enabled: You're warned when potentially unwanted software is downloaded or attempts to install
itself on your computer.
- 2 or Audit

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

Specifies the number of days to keep items in the Quarantine folder. A valid value is an integer
from 0 to 4294967295. The value 0 means items stay in the Quarantine folder indefinitely.

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

Specifies whether to select a random time for the scheduled start and scheduled update for
definitions. Valid values are:

- $true: Scheduled tasks begin within 30 minutes before or after the scheduled time. This is the
default value.
- $false: Scheduled tasks begin on the scheduled time

Randomized start times can distribute the impact of scanning. For example, if several virtual
machines share the same host, randomized start times prevent all virtual machines from starting the
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

Specifies scanning configuration for incoming and outgoing files on NTFS volumes. Valid values are:

- 0 or Both: Scan incoming and outgoing files. This is the default value.
- 1 or Incoming: Scan incoming files only.
- 2 or Outcoming \[SP\]: Scan outgoing files only.

Use this parameter to restrict scanning to incoming or outgoing files on servers that have a large
number of file transfers in only one direction.

Evaluate this configuration based on the server role. For non-NTFS volumes, Windows Defender
does full monitoring of file and program activity.

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

Specifies the day of the week to run scheduled full scans to complete remediation. Valid values are:

- 0 or Everyday
- 1 or Sunday
- 2 or Monday
- 3 or Tuesday
- 4 or Wednesday
- 5 or Thursday
- 6 or Friday
- 7 or Saturday
- 8 or Never (default)

For the value 8 or Never, Windows Defender uses a default frequency to run scheduled full scans to
complete remediation.

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

Specifies the time on the local computer to run scheduled scans for remediation.

To specify a value, enter it as a time span: `hh:mm:ss` where `hh` = hours, `mm` = minutes and `ss`
= seconds. For example, `13:30:00` indicates 1:30 PM.

The default value is `02:00:00` (2:00 AM).

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

Specifies the number of minutes before a detection in the additional action state changes to the
cleared state. A valid value is an integer from 0 to 4294967295.

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

Specifies the number of minutes before a detection in the critically failed state changes to
the additional action state or the cleared state. A valid value is an integer from 0 to 4294967295.

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

Specifies the number of minutes before a detection in the non-critically failed state changes to
the cleared state. A valid value is an integer from 0 to 4294967295.

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

A valid value is an integer from 5 to 100. The default value is 50. The value 0 disables CPU
throttling.

**Note**: This value isn't a hard limit, but rather guidance for the scanning engine to not exceed
the specified value on average.

The value of this parameter is ignored if both of the following conditions are true:

- The value of the **ScanOnlyIfIdleEnabled** parameter is $true (scan only when the computer isn't
in use).
- The value of the **DisableCpuThrottleOnIdleScans** parameter is $false (disable CPU throttling on
idle scans).

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

Specifies whether to start scheduled scans only when the computer is not in use. Valid values are:

- $true: Windows Defender runs schedules scans when the computer is on, but not in use. This is the
default value.
- $false: Windows Defender runs schedules scans when the computer is in use.

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

Specifies the scan type to use during a scheduled scan. Valid values are:

- 1 or QuickScan (default)
- 2 or FullScan

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

Specifies the number of days to keep items in the scan history folder. After this time, Windows
Defender removes the items.

A valid value is an integer from 0 to
4294967295. The default value is 15 days. The value 0 means Windows Defender doesn't remove items from the scan history folder.

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

Specifies the day of the week to run scheduled scans. Valid values are:

- 0 or Everyday
- 1 or Sunday
- 2 or Monday
- 3 or Tuesday
- 4 or Wednesday
- 5 or Thursday
- 6 or Friday
- 7 or Saturday
- 8 or Never (default)

For the value 8 or Never, Windows Defender doesn't do scheduled scans.

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

### -ScanScheduleOffset

Specifies the number of minutes after midnight on the local computer to run scheduled scans. The
default value is 120, which means scheduled scans start on the local computer at 2:00 AM.

If you don't specify a value for this parameter, scheduled scans start at the time specified by the
**ScanScheduleTime** and **ScanScheduleQuickScanTime** parameters.

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

### -ScanScheduleQuickScanTime

Specifies the time on the local computer to run scheduled quick scans.

To specify a value, enter it as a time span: `hh:mm:ss` where `hh` = hours, `mm` = minutes and `ss`
= seconds. For example, `13:30:00` indicates 1:30 PM.

The default value is `02:00:00` (2:00 AM).

If you don't specify a value for this parameter, scheduled quick scans run at the time specified
by the **ScanScheduleOffset** parameter.

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

### -ScanScheduleTime

Specifies the time on the local computer to run scheduled scans.

To specify a value, enter it as a time span: `hh:mm:ss` where `hh` = hours, `mm` = minutes and `ss`
= seconds. For example, `13:30:00` indicates 1:30 PM.

The default value is `02:00:00` (2:00 AM).

If you don't specify a value for this parameter, scheduled scans run at the time specified
by the **ScanScheduleOffset** parameter.

```yaml
Type: DateTime
Aliases: scst
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SchedulerRandomizationTime

Specifies the randomization time for the scheduler. A valid value is an integer from 0 to
4294967295.

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

<!-- Max value claimed to be 1440, but I could set 429496729 --->

Specifies the time interval in minutes for the service health reports to be sent from endpoints.
These reports are for Microsoft Defender Antivirus events 1150 and 1151.

A valid value is an integer from 0 to 4294967295. The default value is 60 minutes. The value 0
means no service health reports are sent.

For more information, see
[Microsoft Defender Antivirus event IDs](/microsoft-365/security/defender-endpoint/troubleshoot-microsoft-defender-antivirus#microsoft-defender-antivirus-event-ids).

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

<!--- Regardless of the value I enter, the property value in Get-MpPreference is 0. If I could
change it like UnknownThreatDefaultAction, I wouldn't be able to change it back.--->

Specifies which automatic remediation action to take for severe level threats. Valid values are:

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
Aliases: stdefac
Accepted values: Clean, Quarantine, Remove, Allow, UserDefined, NoAction, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharedSignaturesPath

Specifies the shared signatures path. For example, `"P:\Signature Data"`. If the value contains
spaces, enclose the value in quotation marks (").

To empty this setting, use the value `" "`.

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

Specified the grace period in minutes that's applied to all signature updates after the initial,
first-time application.

A valid value is an integer from 0 to 4294967295.

If Windows Defender successfully updates within this period, any service initiated updates are
abandoned.

THe **SignatureFirstAuGracePeriod** parameter specifies the grace period when a new signature is
first detected.

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

Specifies the file shares sources for signatures. For example,
`"\\ServerName\\ShareName\Folder name\"`. If the value contains spaces, enclose the value in
quotation marks (").

To empty this setting, use the value `" "`.

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

Specifies the signature update interval. A valid value is an integer from 0 to 4294967295.

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

A valid value uses the following syntax:
`{\\Server1\Share1 | \\Server2\Share2 | ... \\ServerN\ShareN}`.

Windows Defender tries to connect to the shared folders in the specified order. After the update
is successful, Windows Defender stops trying to connect to the remaining shared folders in the
list.

To empty this setting, use the value `" "`.

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

Specifies whether to initiate definition updates even if no antimalware engine is present. Valid values are:

- $true: Windows Defender does not initiate definition updates on startup. This is the default value
- $false: If no antimalware engine is present, Windows Defender initiates definition updates on
startup.

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

Specifies the order in which to contact different definition update sources. The available sources
are:

- InternalDefinitionUpdateServer
- MicrosoftUpdateServer
- MMPC (Microsoft Malware Protection Center)
- FileShares (specified by the **SignatureDefinitionUpdateFileSharesSources** parameter)

A valid value uses the following syntax: `{Source1 | Source2 | Source3 |Source4}`. The default
value is `{MicrosoftUpdateServer | MMPC}`.

Windows Defender tries to connect to the sources in the specified order. After the update
is successful, Windows Defender stops trying to connect to the remaining sources in the list.

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

Specifies the grace period in minutes that's given to a new signature when it's first applied. This
grace period allows more time for compatibility checks with new detection logic. For example, to
prevent false positives from triggering alerts.

A valid value is an integer from 20 to 4320.

If Windows Defender successfully updates within this period, any service initiated updates are
abandoned.

This parameter overrides the value of the **CheckForSignaturesBeforeRunningScan** parameter.

The **SignatureAuGracePeriod** parameter specifies the standard grace period for all subsequent
signature updates.

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

Specifies the day of the week on which to check for definition updates. Valid values are:

- 0 or Everyday
- 1 or Sunday
- 2 or Monday
- 3 or Tuesday
- 4 or Wednesday
- 5 or Thursday
- 6 or Friday
- 7 or Saturday
- 8 or Never (default)

For the value 8 or Never, Windows Defender uses a default frequency to check for definition updates.

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

Specifies the time on the local computer to check for definition updates.

To specify a value, enter it as a time span: `hh:mm:ss` where `hh` = hours, `mm` = minutes and `ss`
= seconds. For example, `13:30:00` indicates 1:30 PM.

If you don't specify a value for this parameter, Windows Defender checks for definition updates 15
minutes before the scheduled scan time by default.

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

A valid value is an integer from 0 to 4294967295. The default value is one day.

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

<!---Range is supposedly 1 to 24 --->

Specifies the interval in hours to check for definition updates.

A valid value is an integer from 0 to 4294967295.

You can use this parameter instead of the **SignatureScheduleDay**and **SignatureScheduleTime**
parameters.

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

Specifies how Windows Defender checks for user consent for certain samples. Valid values are:

- 0 or AlwaysPrompt
- 1 or SendSafeSamples
- 2 or NeverSend
- 3 or SendAllSamples

If consent was previously granted, Windows Defender submits the samples. Otherwise, Windows Defender
prompts the user for consent if the value of the **MAPSReporting** parameter isn't Disabled.

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

Use the **ThreatIDDefaultAction_Ids** and **ThreatIDDefaultAction_Actions** parameters
together in the same command to specify the actions to take on the corresponding threats.

- The **ThreatIDDefaultAction_Ids** parameter identifies the threat from the output of the
**Get-MpThreatCatalog** cmdlet. For example, the ThreatID value of the threat named
**Trojan:Win32/BlueFire** is `3229`.
- The **ThreatIDDefaultAction_Actions** parameter identifies the action to take on the corresponding
threat ID. Valid values are:

  • 1 or Clean

  • 2 or Quarantine

  • 3 or Remove

  • 6 or Allow

  • 8 or UserDefined

  • 9 or NoAction

  • 10 or Block

To replace all existing values with the values you specify, use the following syntax:

`Set-MpPreference -ThreatIDDefaultAction_Ids ThreatID1,ThreatID2,...ThreatIDN -ThreatIDDefaultAction_Actions Action1,Action2,...ActionN`

To add values without affecting existing values, use the **Add-MPPreference** cmdlet:

`Add-MpPreference -ThreatIDDefaultAction_Ids ThreatID1,ThreatID2,...ThreatIDN -ThreatIDDefaultAction_Actions Action1,Action2,...ActionN`

To remove values without affecting other existing values, use the **Remove-MPPreference** cmdlet:

`Remove-MpPreference -ThreatIDDefaultAction_Ids ThreatID1,ThreatID2,...ThreatIDN -ThreatIDDefaultAction_Actions Action1,Action2,...ActionN`

**Note**: When a threat and corresponding action aren't specified in the
**ThreatIDDefaultAction_Ids** and **ThreatIDDefaultAction_Actions** parameters, the action that's
applied to the threat is based on the Security Intelligence Update (SIU). By default, no threats or
corresponding actions are specified in the parameters.

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

Use the **ThreatIDDefaultAction_Ids** and **ThreatIDDefaultAction_Actions** parameters
together in the same command to specify the actions to take on the corresponding threats.

- The **ThreatIDDefaultAction_Ids** parameter identifies the threat from the output of the
**Get-MpThreatCatalog** cmdlet. For example, the ThreatID value of the threat named
**Trojan:Win32/BlueFire** is `3229`.
- The **ThreatIDDefaultAction_Actions** parameter identifies the action to take on the corresponding
threat ID. Valid values are:

  • 1 or Clean

  • 2 or Quarantine

  • 3 or Remove

  • 6 or Allow

  • 8 or UserDefined

  • 9 or NoAction

  • 10 or Block

To replace all existing values with the values you specify, use the following syntax:

`Set-MpPreference -ThreatIDDefaultAction_Ids ThreatID1,ThreatID2,...ThreatIDN -ThreatIDDefaultAction_Actions Action1,Action2,...ActionN`

To add values without affecting existing values, use the **Add-MPPreference** cmdlet:

`Add-MpPreference -ThreatIDDefaultAction_Ids ThreatID1,ThreatID2,...ThreatIDN -ThreatIDDefaultAction_Actions Action1,Action2,...ActionN`

To remove values without affecting other existing values, use the **Remove-MPPreference** cmdlet:

`Remove-MpPreference -ThreatIDDefaultAction_Ids ThreatID1,ThreatID2,...ThreatIDN -ThreatIDDefaultAction_Actions Action1,Action2,...ActionN`

**Note**: When a threat and corresponding action aren't specified in the
**ThreatIDDefaultAction_Ids** and **ThreatIDDefaultAction_Actions** parameters, the action that's
applied to the threat is based on the Security Intelligence Update (SIU). By default, no threats or
corresponding actions are specified in the parameters.

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

Specifies the maximum number of concurrent operations that can be established to run this cmdlet.

A valid value is an integer from 0 to 2147483647. The default value is 0, which means PowerShell
calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are
running on the computer.

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

Specifies whether a CPU usage limit applies scheduled scans only. Valid values are:

- $true: CPU throttling applies only to scheduled scans. This is the default value.
- $false: CPU throttling applies to scheduled and custom scans.

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

Specifies whether to disable UI lockdown mode. Valid values are:

- $true: UI lockdown mode is disabled.
- $false: UI lockdown mode is enabled

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

<!---Default value is 0, which doesn't correspond to anything. If you change it, you can't change
it back to zero. --->

Specifies the automatic remediation action to take for unknown level threats. Valid values are:

- 1 or Clean
- 2 or Quarantine
- 3 or Remove
- 6 or Allow
- 8 or UserDefined
- 9 or NoAction
- 10 or Block

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
