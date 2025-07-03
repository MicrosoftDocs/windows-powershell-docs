---
description: The Remove-MpPreference cmdlet removes exclusions for file name extensions, paths, and processes, or default actions for high, moderate, and low threats.
external help file: MSFT_MpPreference.cdxml-help.xml
Module Name: Defender
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/defender/remove-mppreference?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-MpPreference
---

# Remove-MpPreference

## SYNOPSIS

Removes values from multi-valued properties (for example, exclusions and protected folders) and
returns settings in Windows Defender to their default values.

> [!NOTE]
> You need to run this cmdlet in an elevated PowerShell window (a PowerShell window you opened by
selecting **Run as administrator**).

## SYNTAX

```
Remove-MpPreference
 [-AllowDatagramProcessingOnWinServer]
 [-AllowNetworkProtectionDownLevel]
 [-AllowNetworkProtectionOnWinServer]
 [-AllowSwitchToAsyncInspection]
 [-AsJob]
 [-AttackSurfaceReductionOnlyExclusions <String[]>]
 [-AttackSurfaceReductionRules_Actions <ASRRuleActionType[]>]
 [-AttackSurfaceReductionRules_Ids <String[]>]
 [-CheckForSignaturesBeforeRunningScan]
 [-CimSession <CimSession[]>]
 [-CloudBlockLevel]
 [-CloudExtendedTimeout]
 [-ControlledFolderAccessAllowedApplications <String[]>]
 [-ControlledFolderAccessProtectedFolders <String[]>]
 [-DefinitionUpdatesChannel]
 [-DisableArchiveScanning]
 [-DisableAutoExclusions]
 [-DisableBehaviorMonitoring]
 [-DisableBlockAtFirstSeen]
 [-DisableCacheMaintenance]
 [-DisableCatchupFullScan]
 [-DisableCatchupQuickScan]
 [-DisableCpuThrottleOnIdleScans]
 [-DisableDatagramProcessing]
 [-DisableDnsOverTcpParsing]
 [-DisableDnsParsing]
 [-DisableEmailScanning]
 [-DisableFtpParsing]
 [-DisableGradualRelease]
 [-DisableHttpParsing]
 [-DisableInboundConnectionFiltering]
 [-DisableIntrusionPreventionSystem]
 [-DisableIOAVProtection]
 [-DisableNetworkProtectionPerfTelemetry]
 [-DisablePrivacyMode]
 [-DisableRdpParsing]
 [-DisableRealtimeMonitoring]
 [-DisableRemovableDriveScanning]
 [-DisableRestorePoint]
 [-DisableScanningMappedNetworkDrivesForFullScan]
 [-DisableScanningNetworkFiles]
 [-DisableScriptScanning]
 [-DisableSmtpParsing]
 [-DisableSshParsing]
 [-DisableTlsParsing]
 [-EnableControlledFolderAccess]
 [-EnableConvertWarnToBlock]
 [-EnableDnsSinkhole]
 [-EnableFileHashComputation]
 [-EnableFullScanOnBatteryPower]
 [-EnableLowCpuPriority]
 [-EnableNetworkProtection]
 [-EnableUdpReceiveOffload]
 [-EnableUdpSegmentationOffload]
 [-EngineUpdatesChannel]
 [-ExclusionExtension <String[]>]
 [-ExclusionIpAddress <String[]>]
 [-ExclusionPath <String[]>]
 [-ExclusionProcess <String[]>]
 [-Force]
 [-ForceUseProxyOnly]
 [-HighThreatDefaultAction]
 [-IntelTDTEnabled]
 [-LowThreatDefaultAction]
 [-MAPSReporting]
 [-MeteredConnectionUpdates]
 [-ModerateThreatDefaultAction]
 [-OobeEnableRtpAndSigUpdate]
 [-PlatformUpdatesChannel]
 [-ProxyBypass]
 [-ProxyPacUrl]
 [-ProxyServer]
 [-PUAProtection]
 [-QuarantinePurgeItemsAfterDelay]
 [-RandomizeScheduleTaskTimes]
 [-RealTimeScanDirection]
 [-RemediationScheduleDay]
 [-RemediationScheduleTime]
 [-ReportingAdditionalActionTimeOut]
 [-ReportingCriticalFailureTimeOut]
 [-ReportingNonCriticalTimeOut]
 [-ScanAvgCPULoadFactor]
 [-ScanOnlyIfIdleEnabled]
 [-ScanParameters]
 [-ScanPurgeItemsAfterDelay]
 [-ScanScheduleDay]
 [-ScanScheduleOffset]
 [-ScanScheduleQuickScanTime]
 [-ScanScheduleTime]
 [-SchedulerRandomizationTime]
 [-ServiceHealthReportInterval]
 [-SevereThreatDefaultAction]
 [-SharedSignaturesPath]
 [-SignatureAuGracePeriod]
 [-SignatureBlobFileSharesSources]
 [-SignatureBlobUpdateInterval]
 [-SignatureDefinitionUpdateFileSharesSources]
 [-SignatureDisableUpdateOnStartupWithoutEngine]
 [-SignatureFallbackOrder]
 [-SignatureFirstAuGracePeriod]
 [-SignatureScheduleDay]
 [-SignatureScheduleTime]
 [-SignatureUpdateCatchupInterval]
 [-SignatureUpdateInterval]
 [-SubmitSamplesConsent]
 [-ThreatIDDefaultAction_Actions <ThreatAction[]>]
 [-ThreatIDDefaultAction_Ids <Int64[]>]
 [-ThrottleForScheduledScanOnly]
 [-ThrottleLimit <Int32>]
 [-UILockdown]
 [-UnknownThreatDefaultAction]
 [<CommonParameters>]
```

## DESCRIPTION

The **Remove-MpPreference** cmdlet removes values from multi-valued properties (for example,
exclusions and protected folders) and returns settings in Windows Defender to their default values.

## EXAMPLES

### Example 1

```powershell
Remove-MpPreference -ExclusionPath "C:\Temp"
```

This example removes the folder C:\Temp from the exclusion list.

### Example 2

```powershell
Remove-MpPreference -AttackSurfaceReductionOnlyExclusions "C:\Windows\App.exe"
```

This example excludes only the file app.exe in in the Windows folder on the C drive.

## PARAMETERS

### -AllowDatagramProcessingOnWinServer

Specifies whether to disable the inspection of UDP connections on Windows Server. You don't need to specify a value with
this switch.

**Tip**: This switch works only if the current value of the AllowDatagramProcessingOnWinServer
property is True (enabled). If the value is already False (disabled), this switch does nothing.

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

Specifies whether to disable control of network protection on Windows Server 2016 or Windows Server
2012 R2 by the **EnableNetworkProtection** parameter (Enabled, Disabled, or AuditMode). You don't
need to specify a value with this switch.

**Tip**: This switch works only if the current value of the AllowNetworkProtectionDownLevel
property is True (enabled). If the value is already False (disabled), this switch does nothing.

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

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

Specifies whether to disable control of network protection on Windows Server by the
**EnableNetworkProtection** parameter (Enabled, Disabled, or AuditMode). You don't need to specify a
value with this switch.

**Tip**: This switch works only if the current value of the AllowNetworkProtectionOnWinServer
property is True (enabled). If the value is already False (disabled), this switch does nothing.

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

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

### -AllowSwitchToAsyncInspection

Specifies whether to enable a performance optimization that changes synchronously inspected network
flows to asynchronous inspection after they're checked and validated. You don't need
to specify a value with this switch.

**Tip**: This switch works only if the current value of the AllowSwitchToAsyncInspection
property is False (disabled). If the value is already True (enabled), this switch does nothing.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: astai

Required: False
Position: Named
Default value: None
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

Specifies the existing folders or files to remove from the exclusion list for Attack Surface
Reduction (ASR) rules. Enter a folder path or a fully qualified resource name. For example:

- `"C:\Windows"`
- `"C:\Windows\App.exe"`

To remove values without affecting other existing values, use the following syntax:
`"Value1","Value2",..."ValueN"`

To add values without affecting existing values, use the **Add-MpPreference** cmdlet:

`Add-MpPreference -AttackSurfaceReductionOnlyExclusions "Value1","Value2",..."ValueN"`

To replace all existing values with the values you specify, use the **Set-MpPreference** cmdlet:

`Set-MpPreference -AttackSurfaceReductionOnlyExclusions "Value1","Value2",..."ValueN"`.

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
together in the same command to remove existing attack surface reduction (ASR) rules.

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

To remove values without affecting other existing values, use the following syntax:

`Remove-MpPreference -AttackSurfaceReductionRules_IdsRule1,Rule2,...RuleN -AttackSurfaceReductionRules_Actions Action1,Action2,...ActionN`

For each ID value, there's a corresponding action value. The order determines which action goes with
what ID. The first action goes with the first ID, the second action goes with the second ID,
and so on.

To add values without affecting existing values, use the **Add-MpPreference** cmdlet:

`Add-MpPreference -AttackSurfaceReductionRules_Ids Rule1,Rule2,...RuleN -AttackSurfaceReductionRules_Actions Action1,Action2,...ActionN`

To replace all existing values with the values you specify, use the **Set-MpPreference** cmdlet:

`Set-MpPreference -AttackSurfaceReductionRules_Ids Rule1,Rule2,...RuleN -AttackSurfaceReductionRules_Actions Action1,Action2,...ActionN`

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
together in the same command to remove existing attack surface reduction (ASR) rules.

- The **AttackSurfaceReductionRules_Ids** parameter identifies the ASR rule by GUID value. For
example, the GUID value of the "Block Office communication application from creating child
processes" ASR rule is `26190899-1602-49e8-8b27-eb1d0a1ce869`. For more information, see
[ASR rule to GUID matrix](/defender-endpoint/attack-surface-reduction-rules-reference#asr-rule-to-guid-matrix).
- The **AttackSurfaceReductionRules_Actions** parameter identifies ASR rule action for the
 corresponding ASR rule. Valid values are:

  • 0 or Disabled

  • 1 or Enabled

  • 2 or AuditMode

  • 5 or NotConfigured

  • 6 or Warn

To remove values without affecting other existing values, use the following syntax:

`Remove-MpPreference -AttackSurfaceReductionRules_IdsRule1,Rule2,...RuleN -AttackSurfaceReductionRules_Actions Action1,Action2,...ActionN`

For each ID value, there's a corresponding action value. The order determines which action goes with
what ID. The first action goes with the first ID, the second action goes with the second ID,
and so on.

To add values without affecting existing values, use the **Add-MpPreference** cmdlet:

`Add-MpPreference -AttackSurfaceReductionRules_Ids Rule1,Rule2,...RuleN -AttackSurfaceReductionRules_Actions Action1,Action2,...ActionN`

To replace all existing values with the values you specify, use the **Set-MpPreference** cmdlet:

`Set-MpPreference -AttackSurfaceReductionRules_Ids Rule1,Rule2,...RuleN -AttackSurfaceReductionRules_Actions Action1,Action2,...ActionN`

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

Specifies whether to disable the check for new virus and spyware definitions before Windows Defender
runs a scan. You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the CheckForSignaturesBeforeRunningScan
property is True (enabled). If the value is already False (disabled), the command returns an error.

This parameter applies to scheduled scans, but it has no effect on scans initiated manually from the
user interface from the command line using `mpcmdrun -Scan`.

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

Specifies the value 0 (Default) for the cloud block level that determines how aggressively Microsoft
Defender scans and blocks suspicious files. You don't need to specify a value with this
switch.

**Tip**: This switch works only if the current value of the CloudBlockLevel
property isn't 0. If the value is already 0, this switch does nothing.

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

Specifies the value 0 for the amount of extended time in seconds to block a suspicious file and scan
it in the cloud. You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the CloudExtendedTimeout
property isn't 0. If the value is already 0, this switch does nothing.

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

Specifies the entries to remove from the list of applications that are allowed to make changes in
controlled folders. You can use absolute folder paths (for example `C:\Windows\...`) or environment
variables (for example, `%appdata%...`) for path names.

To remove values without affecting other existing values, use the following syntax:
`"PathAndFileName1","PathAndFileName2",..."PathAndFileNameN"`

To add values without affecting existing values, use the **Add-MpPreference** cmdlet:

`Add-MpPreference -ControlledFolderAccessAllowedApplications "PathAndFileName1","PathAndFileName2",..."PathAndFileNameN"`

To replace all existing values with the values you specify, use the following syntax:
`"PathAndFileName1","PathAndFileName2",..."PathAndFileNameN"`.

To remove custom folders that are protected by controlled folder access, use the
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

Specifies the entries to remove from the list of controlled access folders. You can use absolute
folder paths (for example `C:\Windows\...`) or environment variables (for example, `%appdata%...`)
for path names.

To remove values without affecting other existing values, use the following syntax:
`"Path1","Path2",..."PathN"`

To add values without affecting existing values, use the **Add-MpPreference** cmdlet:

`Add-MpPreference -ControlledFolderAccessAllowedApplications "Path1","Path2",..."PathN"`

To replace all existing values with the values you specify, use the **Set-MpPreference** cmdlet:

`Set-MpPreference -ControlledFolderAccessAllowedApplications"Path1","Path2"..."PathN"`.

To remove applications that are allowed to access controlled folders, use the
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

Specifies the value 0 (NotConfigured) for when devices receive daily Microsoft Defender definition
updates during the monthly gradual rollout. Devices stay up to date automatically during the
gradual release cycle. This value is suitable for most devices.

**Tip**: This switch works only if the current value of the DefinitionUpdatesChannel
property isn't 0 (NotConfigured). If the value is already 0, this switch does nothing.

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

Specifies whether to enable the scanning of archive files (for example, .zip and .cab files) for
malicious and unwanted software. You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the DisableArchiveScanning
property is True (disabled). If the value is already False (enabled), this switch does nothing.

The value True for the DisableArchiveScanning property is available only if Tamper Protection is
disabled. For more information, see [How do I configure or manage Tamper Protection?](https://learn.microsoft.com/defender-endpoint/prevent-changes-to-security-settings-with-tamper-protection#how-do-i-configure-or-manage-tamper-protection).

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

Specifies whether to enable the Automatic Exclusions feature. You don't need to
specify a value with this switch.

**Tip**: This switch works only if the current value of the DisableAutoExclusions
property is True (disabled). If the value is already False (enabled), this switch does nothing.

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

Specifies whether to enable behavior monitoring. You don't need to
specify a value with this switch.

**Tip**: This switch works only if the current value of the DisableBehaviorMonitoring
property is True (disabled). If the value is already False (enabled), this switch does nothing.

The value True for the DisableBehaviorMonitoring property is available only if Tamper Protection is
disabled. For more information, see [How do I configure or manage Tamper Protection?](https://learn.microsoft.com/defender-endpoint/prevent-changes-to-security-settings-with-tamper-protection#how-do-i-configure-or-manage-tamper-protection).

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

Specifies whether to enable block at first seen. You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the DisableBlockAtFirstSeen
property is True (disabled). If the value is already False (enabled), this switch does nothing.

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

### -DisableCacheMaintenance
Specifies whether to enable cache maintenance by the cache maintenance idle task. You don't need to specify a value with
this switch.

**Tip**: This switch works only if the current value of the DisableCacheMaintenance
property is True (disabled). If the value is already False (enabled), this switch does nothing.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: dcm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableCatchupFullScan

Specifies whether to disable catch-up scans for missed scheduled full scans. You don't need to
specify a value with this switch.

**Tip**: This switch works only if the current value of the DisableCatchupFullScan
property is False (enabled). If the value is already True (disabled), this switch does nothing.

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

Specifies whether to disable catch-up scans for missed scheduled quick scans. You don't need to
specify a value with this switch.

**Tip**: This switch works only if the current value of the DisableCatchupQuickScan
property is False (enabled). If the value is already True (disabled), this switch does nothing.

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

Specifies whether to disable CPU throttling for scheduled scans while the device is idle. You don't
need to specify a value with this switch.

**Tip**: This switch works only if the current value of the DisableCpuThrottleOnIdleScans
property is False (enabled). If the value is already True (disabled), this switch does nothing.

This setting doesn't affect other types scheduled scans. Normal CPU throttling occurs on other
types of scheduled scans.

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

Specifies whether to enable inspection of UDP connections. You don't need to specify a value with
this switch.

**Tip**: This switch works only if the current value of the DisableDatagramProcessing
property is True (disabled). If the value is already False (enabled), this switch does nothing.

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

Specifies whether to enable inspection of DNS traffic that occurs over TCP. You don't need to specify a value with this
switch.

**Tip**: This switch works only if the current value of the DisableDnsOverTcpParsing
property is True (disabled). If the value is already False (enabled), this switch does nothing.

Network protection needs to inspect DNS traffic over TCP in the following scenarios:

- To provide metadata for anti-malware behavior monitoring.
- To allow for a DNS sinkhole if the **EnableDnsSinkhole** parameter is set to the value $true.

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

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

Specifies whether to enable inspection of DNS traffic that occurs over UDP. You don't need to
specify a value with this switch.

**Tip**: This switch works only if the current value of the DisableDnsParsing
property is True (disabled). If the value is already False (enabled), this switch does nothing.

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

Specifies whether to disable the parsing of mailbox and email message files to analyze message
bodies and email attachments. You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the DisableEmailScanning
property is False (enabled). If the value is already True (disabled), this switch does nothing.

Windows Defender supports several mailbox and email message file formats. For example:

- .binhex
- .dbx
- .mbx
- .mime
- .pst

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

### -DisableFtpParsing

Specifies whether to enable FTP parsing by network protection. You don't need to specify a value
with this switch.

**Tip**: This switch works only if the current value of the DisableFtpParsing
property is True (disabled). If the value is already False (enabled), this switch does nothing.

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: dftpp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableGradualRelease

Specifies whether to enable gradual rollout of monthly and daily Windows Defender updates. You
don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the DisableGradualRelease
property is True (disabled). If the value is already False (enabled), this switch does nothing.

When you enable this setting, devices remain in the Current Channel unless otherwise specified in
specific channels. The device stays up to date automatically during the gradual release cycle,
which is suitable for most devices.

This setting applies to both monthly and daily updates. This setting overrides configured channel
selections for platform and engine updates.

This policy is available starting with platform version 4.18.2106.5 and later.

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

Specifies whether to enable inspection of HTTP traffic. You don't need to specify a value with this
switch.

**Tip**: This switch works only if the current value of the DisableHttpParsing
property is True (disabled). If the value is already False (enabled), this switch does nothing.

If the value of the **EnableNetworkProtection** parameter is `Enabled`, HTTP connections to
malicious websites can be blocked.

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

Specifies whether to enable inspection of inbound connections by network protection. You don't need
to specify a value with this switch.

**Tip**: This switch works only if the current value of the DisableInboundConnectionFiltering
property is True (disabled). If the value is already False (enabled), this switch does nothing.

When you enable this setting, network protection inspects inbound and outbound connections. This is
the default value.

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

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

Specifies whether to enable the intrusion prevention system in network protection. You don't need
to specify a value with this switch.

**Tip**: This switch works only if the current value of the DisableIntrusionPreventionSystem
property is True (disabled). If the value is already False (enabled), this switch does nothing.

When this setting is enabled, the system is protected against the exploitation of known
vulnerabilities.

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

Specifies whether to enable the automatic scanning of all downloaded files and attachments. You don't need to
specify a value with this switch.

**Tip**: This switch works only if the current value of the DisableIOAVProtection
property is True (disabled). If the value is already False (enabled), this switch does nothing.

The value True for the DisableIOAVProtection property is available only if Tamper Protection is
disabled. For more information, see [How do I configure or manage Tamper Protection?](https://learn.microsoft.com/defender-endpoint/prevent-changes-to-security-settings-with-tamper-protection#how-do-i-configure-or-manage-tamper-protection).

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

### -DisableNetworkProtectionPerfTelemetry

Specifies whether to enable the gathering and sending of performance telemetry from Network
Protection. You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the DisableNetworkProtectionPerfTelemetry
property is True (disabled). If the value is already False (enabled), this switch does nothing.

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: dnppt

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisablePrivacyMode

**Note**: This switch is a legacy setting that doesn't affect current platforms.

The intent of this switch was to enable privacy mode if it was disabled. Disabled privacy mode
prevented users (not admins) from displaying the threat history.

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

Specifies whether to enable parsing RDP traffic to look for malicious attacks using the RDP
protocol. You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the DisableRdpParsing
property is True (disabled). If the value is already False (enabled), this switch does nothing.

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

Specifies whether to enable real-time protection. You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the DisableRealtimeMonitoring
property is True (disabled). If the value is already False (enabled), this switch does nothing.

The default and recommended value for this setting is enabled (False).

The value True for the DisableRealtimeMonitoring property is available only if Tamper Protection is
disabled. For more information, see [How do I configure or manage Tamper Protection?](https://learn.microsoft.com/defender-endpoint/prevent-changes-to-security-settings-with-tamper-protection#how-do-i-configure-or-manage-tamper-protection).

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

Specifies whether to disable scanning for malicious and unwanted software on removable drives (for
example, flash drives) during a full scan (quick scans and custom scans aren't affected). You don't
need to specify a value with this switch.

**Tip**: This switch works only if the current value of the DisableRemovableDriveScanning
property is False (enabled). If the value is already True (disabled), this switch does nothing.

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

Specifies whether to disable scanning of restore points. You don't need to specify a value with this
switch.

**Tip**: This switch works only if the current value of the DisableRestorePoint
property is False (enabled). If the value is already True (disabled), this switch does nothing.

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

Specifies whether to disable scanning mapped network drives. You don't need to specify a value with
this switch.

**Tip**: This switch works only if the current value of the DisableScanningMappedNetworkDrivesForFullScan
property is False (enabled). If the value is already True (disabled), this switch does nothing.

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

Specifies whether to enable scanning network files. You don't need to specify a value with
this switch.

**Tip**: This switch works only if the current value of the DisableScanningNetworkFiles
property is True (disabled). If the value is already False (enabled), this switch does nothing.

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

Specifies whether to enable the scanning of scripts during malware scans. You don't need to specify
a value with this switch.

**Tip**: This switch works only if the current value of the DisableScriptScanning
property is True (disabled). If the value is already False (enabled), this switch does nothing.

The value True for the DisableScriptScanning property is available only if Tamper Protection is
disabled. For more information, see [How do I configure or manage Tamper Protection?](https://learn.microsoft.com/defender-endpoint/prevent-changes-to-security-settings-with-tamper-protection#how-do-i-configure-or-manage-tamper-protection).

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

### -DisableSmtpParsing

Specifies whether to enable SMTP parsing by network protection. You don't need to specify a value
with this switch.

**Tip**: This switch works only if the current value of the DisableSmtpParsing
property is True (disabled). If the value is already False (enabled), this switch does nothing.

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: dsmtpp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableSshParsing

Specifies whether to enable the inspection of SSH traffic. You don't need to specify
a value with this switch.

**Tip**: This switch works only if the current value of the DisableSshParsing
property is True (disabled). If the value is already False (enabled), this switch does nothing.

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

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

Specifies whether to enable the inspection of TLS traffic. You don't need to specify
a value with this switch.

**Tip**: This switch works only if the current value of the DisableTlsParsing
property is True (disabled). If the value is already False (disabled), this switch does nothing.

When this setting is False (disabled) Network protection inspects TLS traffic (also known as HTTPS
traffic) to see if a connection is being made to a malicious website, and to provide metadata to
behavior monitoring.

TLS connections to malicious websites can also be blocked if the value of the
**EnableNetworkProtection** parameter is `Enabled`.

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

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

Specifies whether to disable the controlled folder access feature. You don't need to specify a value
with this switch.

**Tip**: This switch works only if the current value of the EnableControlledFolderAccess
property isn't 0 (Disabled). If the value is already 0, this switch does nothing.

To remove folders that are protected by controlled folder access, use the
**ControlledFolderAccessProtectedFolders** parameter.

To remove applications that are allowed to access controlled folders, use the
**ControlledFolderAccessAllowedApplications** parameter.

For more information about controlled folder access, see [Protect important folders with controlled
folder access](/defender-endpoint/controlled-folders).

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

### -EnableConvertWarnToBlock

Specifies whether to disable blocking network traffic by network protection instead of displaying a
warning. You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the EnableConvertWarnToBlock
property is True (enabled). If the value is already False (disabled), this switch does nothing.

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ecwtb

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableDnsSinkhole

**Note**: This parameter has been deprecated.

Specifies whether to enable examining DNS traffic to detect and sinkhole DNS exfiltration attempts
and other DNS based malicious attacks. You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the EnableDnsSinkhole
property is False (disabled). If the value is already True (enabled), this switch does nothing.

When this setting is enabled. network protection can inspect the DNS traffic of a machine and,
in conjunction with behavior monitoring, detect and sinkhole DNS exfiltration attempts, and other
DNS based malicious attacks.

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

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

Specifies whether to disable file hash computation for scanned files. You don't need to specify a
value with this switch.

**Tip**: This switch works only if the current value of the EnableFileHashComputation
property is True (enabled). If the value is already False (disabled), this switch does nothing.

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

Specifies whether to disable full scans while on battery power. You don't need to specify a value
with this switch.

**Tip**: This switch works only if the current value of the EnableFullScanOnBatteryPower
property is True (enabled). If the value is already False (disabled), this switch does nothing.

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

Specifies whether to disable using low CPU priority for scheduled scans. You don't need to specify
a value with this switch.

**Tip**: This switch works only if the current value of the EnableLowCpuPriority
property is True (enabled). If the value is already False (disabled), this switch does nothing.

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

Specifies whether to disable the network protection service. You don't need to specify a value with
this switch.

**Tip**: This switch works only if the current value of the EnableNetworkProtection
property isn't 0 (Disabled). If the value is already 0, this switch does nothing.

For more information about network protection, see [Protect your network](/defender-endpoint/network-protection).

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

### -EnableUdpReceiveOffload

Specifies whether to disable UDP receive offload support in network protection. You don't need to
specify a value with this switch.

**Tip**: This switch works only if the current value of the EnableUdpReceiveOffload
property is True (enabled). If the value is already False (disabled), this switch does nothing.

Starting with platform version `4.18.24030`, we're gradually moving the default value of this
setting to True (enabled).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: euro

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableUdpSegmentationOffload

Specifies whether to disable UDP segmentation offload support in network protection (the value 0 or
Disabled). You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the EnableUdpSegmentationOffload
property is True (enabled). If the value is already False (disabled), this switch does nothing.

Starting with platform version `4.18.24030`, we're gradually moving the default value to $true
(enabled).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: euso

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EngineUpdatesChannel

Specifies that devices receive Microsoft Defender engine updates automatically during the gradual
release cycle (the value 0 or NotConfigured). This value is suitable for most devices. You don't
need to specify a value with this switch.

**Tip**: This switch works only if the current value of the EngineUpdatesChannel
property isn't 0 (NotConfigured). If the value is already 0, this switch does nothing.

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

Specifies the filename extensions (for example, `obj` or `lib`) to remove from the list of
exclusions from scheduled, custom, and real-time scanning.

To remove values without affecting other existing values, use the following syntax:
`"Extension1","Extension2"..."ExtensionN"`

To add values without affecting existing values, use the **Add-MpPreference** cmdlet:

`Add-MpPreference -ExclusionExtension "Extension1","Extension2"..."ExtensionN"`

To replace all existing values with the values you specify, use the **Set-MpPreference** cmdlet:

`Set-MpPreference -ExclusionExtension "Extension1","Extension2",..."ExtensionN"`.

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
Specifies the IP addresses to remove from the list of exclusions from scheduled, custom, and
real-time scanning.

To remove values without affecting other existing values, use the following syntax:
`"IPAddress1","IPAddress2",..."IPAddressN"`

To add values without affecting existing values, use the **Add-MpPreference** cmdlet:

`Add-MpPreference -ExclusionIpAddress "IPAddress1","IPAddress",..."IPAddressN"`

To replace all existing values with the values you specify, use the **Set-MpPreference** cmdlet:

`Set-MpPreference -ExclusionIpAddress "IPAddress1","IPAddress2",..."IPAddresseN"`.

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

Specifies the path and filename or path only entries to remove from the list of exclusions from
scheduled and real-time scanning.

To remove values without affecting other existing values, use the following syntax:
`"Value1","Value2",..."ValueN"`

To add values without affecting existing values, use the **Add-MpPreference** cmdlet:

`Add-MpPreference -ExclusionPath "Value1","Value2",..."ValuehN"`

To replace all existing values with the values you specify, use the **Set-MpPreference** cmdlet:

`Set-MpPreference -ExclusionPath "Value1","Value2"..."ValueN"`.

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

Specifies the path to process image entries to remove from the list of exclusions from scheduled
and real-time scanning.

To remove values without affecting other existing values, use the following syntax:
`"Path1","Path2",..."PathN"`

To add values without affecting existing values, use the **Add-MpPreference** cmdlet:

`Add-MpPreference -ExclusionProcess "Path1","Path2",..."PathhN"`

To replace all existing values with the values you specify, use the **Set-MpPreference** cmdlet:

`Set-MpPreference -ExclusionProcess "Path1","Path2"..."PathN"`.

Process image entries exclude files opened by executable programs only, not the processes
themselves. To remove processes from the list of exclusions, use the **ExclusionPath** parameter.

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

Specifies the device isn't forced to use the proxy only (the value $false). You don't need to
specify a value with this switch.

**Tip**: This switch works only if the current value of the ForceUseProxyOnly
property is True (enabled). If the value is already False (disabled), this switch does nothing.

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

Specifies the remediation action value 0 for high level threats. You don't need to
specify a value with this switch.

**Tip**: This switch works only if the current value of the HighThreatDefaultAction
property isn't 0. If the value is already 0, this switch does nothing.

The value 0 means Windows Defender uses the default action based on the Security
Intelligence Update (SIU) definitions to determine how to handle the detected threat.

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

### -IntelTDTEnabled

Specifies Intel Threat Detection Technology (TDT) integration in Windows Defender is controlled by
the system (typically, disabled). You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the IntelTDTEnabled
property isn't blank (default behavior controlled by the system). If the value is already blank,
this switch does nothing.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: itdte

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LowThreatDefaultAction

Specifies the remediation action value 0 for low level threats. You don't need to
specify a value with this switch.

**Tip**: This switch works only if the current value of the LowThreatDefaultAction
property isn't 0. If the value is already 0, this switch does nothing.

The value 0 means Windows Defender uses the default action based on the Security
Intelligence Update (SIU) definitions to determine how to handle the detected threat.

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

Specifies Advanced membership (2) in the Microsoft Active Protection Service. You don't need to
specify a value with this switch.

**Tip**: This switch works only if the current value of the MAPSReporting
property isn't 2 (Advanced). If the value is already 2, this switch does nothing.

MAPS is an online community that helps you choose how to respond to potential threats. The community
also helps prevent the spread of new malicious software.

The value 2 or Advanced for this setting sends the following information about detected software to
Microsoft:

- Where the software came from.
- Actions you applied (manually or automatically).
- Whether the action succeeded.
- The location of the software.
- Filenames.
- How the software operates.
- How the software affected your computer.

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

Specifies whether to disable updates to Windows Defender over metered connections. You don't need to
specify a value with this switch.

**Tip**: This switch works only if the current value of the MeteredConnectionUpdates
property is True (enabled). If the value is already False (disabled), this switch does nothing.

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

Specifies the automatic remediation action value 0 for moderate level threats. You don't need to
specify a value with this switch.

**Tip**: This switch works only if the current value of the ModerateThreatDefaultAction
property isn't 0. If the value is already 0, this switch does nothing.

The value 0 means Windows Defender uses the default action based on the Security
Intelligence Update (SIU) definitions to determine how to handle the detected threat.

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

### -OobeEnableRtpAndSigUpdate

Specifies whether to disable real-time protection and Security Intelligence Updates during Out of
Box experience (OOBE). You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the OobeEnableRtpAndSigUpdate
property is True (enabled). If the value is already False (disabled), this switch does nothing.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: oobers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PlatformUpdatesChannel

Specifies that devices receive Microsoft Defender platform updates automatically during the gradual
release cycle (the value 0 or NotConfigured). This value is suitable for most devices. You don't
need to specify a value with this switch.

**Tip**: This switch works only if the current value of the PlatformUpdatesChannel
property isn't 0 (NotConfigured). If the value is already 0, this switch does nothing.

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

Specifies whether to empty the list of entries for proxy bypass. You don't need to specify a value
with this switch.

To replace all existing values with the values you specify, use the **Set-MpPreference** cmdlet:

`Set-MpPreference -ProxyBypass "Value1","Value2",..."ValueN"`.

To add values without affecting existing values, run the following commands:

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

Specifies whether to remove the Privilege Attribute Certificate (PAC) proxy value. You don't need
to specify a value with this switch.

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

Specifies whether to remove the proxy server value. You don't need to specify a value with this
switch.

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

Specifies whether to disable detection for potentially unwanted applications (the value 0 or
Disabled). You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the PUAProtection
property isn't 0 (Disabled). If the value is already 0, this switch does nothing.

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

Specifies the value 0 as the number of days to keep items in the Quarantine folder
before they're automatically removed. You don't need to specify a value with this switch.

The value 0 means items stay in the Quarantine folder indefinitely (items aren't automatically
removed).

**Tip**: This switch works only if the current value of the QuarantinePurgeItemsAfterDelay
property isn't 0. If the value is already 0, this switch does nothing.

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

Specifies whether to enable selecting a random time within 30 minutes before or after scheduled task
times (the value True). You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the RandomizeScheduleTaskTimes
property is False (disabled). If the value is already True (enabled), this switch does nothing.

Randomized start times can distribute the impact of scanning. For example, if several virtual
machines share the same host, randomized start times prevent all virtual machines from starting the
scheduled tasks at the same time.

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

Specifies scanning for incoming and outgoing files on NTFS volumes (the value 0 or Both). You don't
need to specify a value with this switch.

**Tip**: This switch works only if the current value of the RealTimeScanDirection
property isn't 0. If the value is already 0, this switch does nothing.

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

Specifies running scheduled full scans every day to complete remediation (the value 0 or Everyday).
You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the RemediationScheduleDay
property isn't 0 (Everyday). If the value is already 0, this switch does nothing.

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

Specifies `02:00:00` (2:00 AM) as the time on the local computer to run scheduled scans for
remediation. You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the RemediationScheduleTime
property isn't `02:00:00` (2:00 AM). If the value is already `02:00:00`, this switch does nothing.

The value of this parameter is meaningful only if the value of the **RemediationScheduleDay**
parameter isn't 8 or Never.

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

Specifies 10080 as the number of minutes that Windows Defender waits before detections that require
additional action time out (detections in the additional action state change to the cleared state).
You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the ReportingAdditionalActionTimeOut
property isn't 10080. If the value is already 10080, this switch does nothing.

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

Specifies 10080 as the number of minutes that Windows Defender waits before reporting a critical
failure (detections in the critically failed state change to the additional action state or the
cleared state).

**Tip**: This switch works only if the current value of the ReportingCriticalFailureTimeOut
property isn't 10080. If the value is already 10080, this switch does nothing.

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

Specifies 1440 as the number of minutes that Windows Defender waits before reporting a non-critical
failure (detections in the non-critically failed state change the cleared state).

**Tip**: This switch works only if the current value of the ReportingNonCriticalTimeOut
property isn't 1440. If the value is already 1440, this switch does nothing.

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

Specifies 50 as the maximum percentage CPU usage for a scan. You don't need to specify a value with
this switch.

**Tip**: This switch works only if the current value of the ScanAvgCPULoadFactor
property isn't 50. If the value is already 50, this switch does nothing.

This value isn't a hard limit, but rather guidance for the scanning engine to not exceed
the specified value on average.

The value of this setting is ignored if both of the following conditions are true:

- The value of the **ScanOnlyIfIdleEnabled** setting is True (scan only when the computer isn't
in use).
- The value of the **DisableCpuThrottleOnIdleScans** setting is True (disable CPU throttling on
idle scans).

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

Specifies whether to enable starting scheduled scans only when the computer is not in use. You
don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the ScanOnlyIfIdleEnabled
property is False (disabled). If the value is already True (enabled), this switch does nothing.

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

Specifies quick scan as the scan type to use during a scheduled scan (the value 1 or QuickScan). You
don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the ScanParameters
property is 2 (FullScan). If the value is already 1 (QuickScan), this switch does nothing.

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

Specifies 15 as the number of days to keep items in the scan history folder. After this time,
Windows Defender removes the items. You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the ScanPurgeItemsAfterDelay
property isn't 15. If the value is already 15, this switch does nothing.

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

Specifies running full scans every day (the value 0 or Everyday). You don't need to specify a value
with this switch.

**Tip**: This switch works only if the current value of the ScanScheduleDay
property isn't 0 (Everyday). If the value is already 0, this switch does nothing.

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

### -ScanScheduleOffset

Specifies 120 as the fixed number of minutes to delay scheduled scan start times on the device. You
don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the ScanScheduleOffset
property isn't 120. If the value is already 120, this switch does nothing.

The value 120 for this setting means sScheduled scans on this device start 2 hours after the times
specified by the **ScanScheduleTime** and **ScanScheduleQuickScanTime** settings.

Scheduled scans are also affected by the **SchedulerRandomizationTime** parameter.

Staggering start times on devices can help reduce the impact on network and system performance.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: scso

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScanScheduleQuickScanTime

Specifies `00:00:00` (12:00 AM) as the time on the local computer to run scheduled quick scans. You
don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the ScanScheduleQuickScanTime
property isn't `00:00:00` (12:00 AM). If the value is already `00:00:00` this switch does nothing.

The time scheduled quick scans start is also affected by the value of the **ScanScheduleOffset**
and **SchedulerRandomizationTime** parameters.

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

Specifies `02:00:00` (2:00 AM) as the time on the local computer to run scheduled full scans. You
don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the ScanScheduleTime
property isn't `02:00:00` (2:00 AM). If the value is already `02:00:00` this switch does nothing.

The time scheduled full scans start is also affected by the value of the **ScanScheduleOffset**
and **SchedulerRandomizationTime** parameters.

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

Specifies 4 minutes as the time window within which scheduled tasks in Microsoft Defender (for
example, scans and updates) can randomly start. You don't need to specify a value with this switch.

Scheduled tasks can start within the specified number of minutes before or
after the time of the scheduled task.

The randomization time window is used around specific start time value (for example, the
**ScanScheduleTime** and **ScanScheduleQuickScanTime** parameters) or around the number of minutes
specified by the **ScanScheduleOffset** parameter.

Staggering start times on devices can help reduce the impact on network and system performance.

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

### -ServiceHealthReportInterval

Specifies the time interval in minutes for the service health reports to be sent from endpoints.
These reports are for Microsoft Defender Antivirus events 1150 and 1151.

A valid value is an integer from 0 to 4294967295. The default value is 60 minutes. The value 0
means no service health reports are sent.

For more information, see
[Microsoft Defender Antivirus event IDs](/microsoft-365/security/defender-endpoint/troubleshoot-microsoft-defender-antivirus#microsoft-defender-antivirus-event-ids).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: shri

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SevereThreatDefaultAction

Specifies the remediation action value 0 for severe level threats. You don't need to
specify a value with this switch.

**Tip**: This switch works only if the current value of the SevereThreatDefaultAction
property isn't 0. If the value is already 0, this switch does nothing.

The value 0 means Windows Defender uses the default action based on the Security
Intelligence Update (SIU) definitions to determine how to handle the detected threat.

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

Specifies whether to remove the shared signatures path value. You don't need to specify a value with
this switch.

The value of this setting is meaningful only if the **SignatureFallBackOrder** parameter contains
the value `FileShares`.

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

Specifies the value 0 minutes for the grace period applied to all signature updates after the
initial, first-time application. You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the SignatureAuGracePeriod
property isn't 0. If the value is already 0, this switch does nothing.

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

Specifies whether to remove the file share sources for signatures blob files. You don't need to specify a value with
this switch.

The value of this setting is meaningful only if the **SignatureFallBackOrder** parameter contains
the value `FileShares`.

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

Specifies the value 60 minutes for checking and updating signature blob files. You don't need to
specify a value with this switch.

**Tip**: This switch works only if the current value of the SignatureBlobUpdateInterval
property isn't 60. If the value is already 60, this switch does nothing.

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

Specifies whether to remove the file share sources for signature definition update files. You don't
need to specify a value with this switch.

The value of this setting is meaningful only if the **SignatureFallBackOrder** parameter contains
the value `FileShares`.

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

Specifies whether to enable signature updates on startup when the Windows Defender engine isn't
available. You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the SignatureDisableUpdateOnStartupWithoutEngine
property is True (disabled). If the value is already False (enabled), this switch does nothing.

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

Specifies the value `{MicrosoftUpdateServer|MMPC}` as the order in which to contact different
definition update sources. You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the SignatureFallbackOrder
property isn't `{MicrosoftUpdateServer|MMPC}`. If the value is already
`{MicrosoftUpdateServer|MMPC}`, this switch does nothing.

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

Specifies the value 120 minutes (2 hours) for the grace period in minutes immediately after the
first installation of the service, during which any service-initiated signature update is aborted if
the update occurs successfully within this amount of time.  You don't need to specify a value with
this switch.

**Tip**: This switch works only if the current value of the SignatureFirstAuGracePeriod
property isn't 120. If the value is already 120, this switch does nothing.

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

Specifies the value 8 or Never for the day of the week that Windows Defender checks for definition
updates. You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the SignatureScheduleDay
property isn't 8. If the value is already 8, this switch does nothing.

Although the value 8 or Never means Windows Defender doesn't check for updates on specific days,
definition updates still happen through other means (for example, manual updates or other system
events).

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

Specifies the value `01:45:00` (1:45 AM) for the time on the local computer to check for definition
updates. You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the SignatureScheduleTime
property isn't `01:45:00`. If the value is already `01:45:00`, this switch does nothing.

The value of this setting is meaningful only if the value of the **SignatureScheduleDay** isn't 8
or Never (the default value).

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

### -SignatureUpdateCatchupInterval

Specifies the value 1 (one day) for catching up on missed signature updates. You don't need to
specify a value with this switch.

**Tip**: This switch works only if the current value of the SignatureUpdateCatchupInterval
property isn't 1. If the value is already 1, this switch does nothing.

Even when the value of the **SignatureScheduleDay** setting is 8 or Never (the default value),
this setting still controls the behavior of updates through other means (for example, manual
updates or other system events).

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

Specifies the value 0 as the interval in hours to check for definition updates. You don't need to
specify a value with this switch.

**Tip**: This switch works only if the current value of the SignatureUpdateInterval
property isn't 0. If the value is already 0, this switch does nothing.

The value 0 means Windows Defender uses the default interval for update checks, which is typically
every 24 hours.

Even when the value of the **SignatureScheduleDay** setting is 8 or Never (the default value),
this setting still controls the behavior of updates through other means (for example, manual
updates or other system events).

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

Specifies the value 0 or AlwaysPrompt as the interval in hours to check for definition updates.
You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the SubmitSamplesConsent
property isn't 0. If the value is already 0, this switch does nothing.

If consent was previously granted, Windows Defender submits the samples. Otherwise, Windows Defender
prompts the user for consent if the value of the **MAPSReporting** parameter isn't Disabled.

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

Use the **ThreatIDDefaultAction_Ids** and **ThreatIDDefaultAction_Actions** parameters
together in the same command to remove the actions to take on the corresponding threats.

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

To remove values without affecting other existing values, use the following syntax:

`Remove-MpPreference -ThreatIDDefaultAction_Ids ThreatID1,ThreatID2,...ThreatIDN -ThreatIDDefaultAction_Actions Action1,Action2,...ActionN`

For each ID value, there's a corresponding action value. The order determines which action goes with
what ID. The first action goes with the first ID, the second action goes with the second ID,
and so on.

To add values without affecting existing values, use the **Add-MpPreference** cmdlet:

`Add-MpPreference -ThreatIDDefaultAction_Ids ThreatID1,ThreatID2,...ThreatIDN -ThreatIDDefaultAction_Actions Action1,Action2,...ActionN`

To replace all existing values with the values you specify, use the **Set-MpPreference** cmdlet:

`Set-MpPreference -ThreatIDDefaultAction_Ids ThreatID1,ThreatID2,...ThreatIDN -ThreatIDDefaultAction_Actions Action1,Action2,...ActionN`

**Note**: When a threat and corresponding action aren't specified in the
**ThreatIDDefaultAction_Ids** and **ThreatIDDefaultAction_Actions** parameters, the action that's
applied to the threat is based on the Security Intelligence Update (SIU). By default, no threats or
corresponding actions are specified in the parameters.

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

Use the **ThreatIDDefaultAction_Ids** and **ThreatIDDefaultAction_Actions** parameters
together in the same command to remove the actions to take on the corresponding threats.

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

To remove values without affecting other existing values, use the following syntax:

`Remove-MpPreference -ThreatIDDefaultAction_Ids ThreatID1,ThreatID2,...ThreatIDN -ThreatIDDefaultAction_Actions Action1,Action2,...ActionN`

For each ID value, there's a corresponding action value. The order determines which action goes with
what ID. The first action goes with the first ID, the second action goes with the second ID,
and so on.

To add values without affecting existing values, use the **Add-MpPreference** cmdlet:

`Add-MpPreference -ThreatIDDefaultAction_Ids ThreatID1,ThreatID2,...ThreatIDN -ThreatIDDefaultAction_Actions Action1,Action2,...ActionN`

To replace all existing values with the values you specify, use the **Set-MpPreference** cmdlet:

`Set-MpPreference -ThreatIDDefaultAction_Ids ThreatID1,ThreatID2,...ThreatIDN -ThreatIDDefaultAction_Actions Action1,Action2,...ActionN`

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

### -ThrottleForScheduledScanOnly

Specifies whether to apply CPU throttling to scheduled scans only (custom scans aren't affected).
You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the ThrottleForScheduledScanOnly
property is False (CPU throttling applies to scheduled scans and custom scans). If the value is
already True (CPU throttling applies to scheduled scans only), this switch does nothing.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: tfsso

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

### -UILockdown

Specifies whether to disable UI lockdown mode. You don't need to specify a value with this switch.

**Tip**: This switch works only if the current value of the UILockdown
property is True (enabled). If the value is already False (disabled), this switch does nothing.

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

Specifies the remediation action value 0 for unknown level threats. You don't need to
specify a value with this switch.

**Tip**: This switch works only if the current value of the UnknownThreatDefaultAction
property isn't 0. If the value is already 0, this switch does nothing.

The value 0 means Windows Defender uses the default action based on the Security
Intelligence Update (SIU) definitions to determine how to handle the detected threat.

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
