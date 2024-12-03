---
description: The Add-MpPreference cmdlet modifies settings for Windows Defender.
external help file: MSFT_MpPreference.cdxml-help.xml
Module Name: Defender
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/defender/add-mppreference?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-MpPreference
---

# Add-MpPreference

## SYNOPSIS
Modifies settings for Windows Defender.

> [!NOTE]
> You need to run this cmdlet in an elevated PowerShell window (a PowerShell window you opened by
selecting **Run as administrator**).

## SYNTAX

```
Add-MpPreference
 [-AsJob]
 [-AttackSurfaceReductionOnlyExclusions <String[]>]
 [-AttackSurfaceReductionRules_Actions <ASRRuleActionType[]>]
 [-AttackSurfaceReductionRules_Ids <String[]>]
 [-CimSession <CimSession[]>]
 [-ControlledFolderAccessAllowedApplications <String[]>]
 [-ControlledFolderAccessProtectedFolders <String[]>]
 [-ExclusionExtension <String[]>]
 [-ExclusionIpAddress <String[]>]
 [-ExclusionPath <String[]>]
 [-ExclusionProcess <String[]>]
 [-Force]
 [-ThreatIDDefaultAction_Actions <ThreatAction[]>]
 [-ThreatIDDefaultAction_Ids <Int64[]>]
 [-ThrottleLimit <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Add-MpPreference` cmdlet modifies settings for Windows Defender. Use this cmdlet to add
exclusions for file name extensions, paths, and processes, and to add default actions for high,
moderate, and low threats.

## EXAMPLES

### Example 1: Add a folder to the exclusion list

```powershell
Add-MpPreference -ExclusionPath 'C:\Temp'
```

This example adds the folder `C:\Temp` to the exclusion list.

### Example 2: Allow an application to access folders

```powershell
Add-MpPreference -ControlledFolderAccessAllowedApplications 'c:\apps\test.exe'
```

This example allows the specified application to make changes in controlled folders.

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

### -AttackSurfaceReductionOnlyExclusions

Specifies the folders or files to add to the exclusion list for Attack Surface
Reduction (ASR) rules. Enter a folder path or a fully qualified resource name. For example:

- `"C:\Windows"`
- `"C:\Windows\App.exe"`

To add values without affecting existing values, use the following syntax:
"Value1","Value2",..."ValueN"`

To remove values without affecting other existing values, use the **Remove-MpPreference** cmdlet:
`Remove-MpPreference -AttackSurfaceReductionOnlyExclusions "Value1","Value2",..."ValueN"`

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
together in the same command to add attack surface reduction (ASR) rules.

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

To add values without affecting existing values, use the following syntax:

`Add-MpPreference -AttackSurfaceReductionRules_Ids Rule1,Rule2,...RuleN Rule1,Rule2,...RuleN -AttackSurfaceReductionRules_Actions Action1,Action2,...ActionN`

To remove values without affecting other existing values, use the **Remove-MPPreference** cmdlet:

`Remove-MPPreference -AttackSurfaceReductionRules_Ids Rule1,Rule2,...RuleN -AttackSurfaceReductionRules_Actions Action1,Action2,...ActionN`

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
together in the same command to add attack surface reduction (ASR) rules.

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

To add values without affecting existing values, use the following syntax:

`Add-MpPreference -AttackSurfaceReductionRules_Ids Rule1,Rule2,...RuleN Rule1,Rule2,...RuleN -AttackSurfaceReductionRules_Actions Action1,Action2,...ActionN`

To remove values without affecting other existing values, use the **Remove-MPPreference** cmdlet:

`Remove-MPPreference -AttackSurfaceReductionRules_Ids Rule1,Rule2,...RuleN -AttackSurfaceReductionRules_Actions Action1,Action2,...ActionN`

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

### -ControlledFolderAccessAllowedApplications

Specifies the entries to add to the list of applications that are allowed to make changes in
controlled folders. You can use absolute folder paths (for example `C:\Windows\...`) or environment
variables (for example, `%appdata%...`) for path names.

To add values without affecting other existing values, use the following syntax:
`"PathAndFileName1","PathAndFileName2",..."PathAndFileNameN"`

To remove values without affecting existing values, use the **Remove-MPPreference** cmdlet:

`Remove-MpPreference -ControlledFolderAccessAllowedApplications "PathAndFileName1","PathAndFileName2",..."PathAndFileNameN"`

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

Specifies the entries to add to the list of controlled access folders. You can use absolute
folder paths (for example `C:\Windows\...`) or environment variables (for example, `%appdata%...`)
for path names.

To add values without affecting existing values, use the following syntax:
`"Path1","Path2",..."PathN"`

To remove values without affecting other existing values, use the **Remove-MpPreference** cmdlet:

`Remove-MpPreference -ControlledFolderAccessAllowedApplications "Path1","Path2",..."PathN"`

To replace all existing values with the values you specify, use the **Set-MPPreference** cmdlet:

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

### -ExclusionExtension

Specifies the filename extensions (for example, `obj` or `lib`) to add to the list of
exclusions from scheduled, custom, and real-time scanning.

To add values without affecting other existing values, use the following syntax:
`"Extension1","Extension2"..."ExtensionN"`

To remove values without affecting existing values, use the **Remove-MPPreference** cmdlet:

`Remove-MpPreference -ExclusionExtension "Extension1","Extension2"..."ExtensionN"`

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

Specifies the IP addresses to add to the list of exclusions from scheduled, custom, and
real-time scanning.

To add values without affecting other existing values, use the following syntax:
`"IPAddress1","IPAddress2",..."IPAddressN"`

To remove values without affecting existing values, use the **Remove-MPPreference** cmdlet:

`Remove-MpPreference -ExclusionIpAddress "IPAddress1","IPAddress",..."IPAddressN"`

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

Specifies the path and filename or path only entries to add to the list of exclusions from
scheduled and real-time scanning.

To add values without affecting other existing values, use the following syntax:
`"Value1","Value2",..."ValueN"`

To remove values without affecting existing values, use the **Remove-MPPreference** cmdlet:

`Remove-MpPreference -ExclusionPath "Value1","Value2",..."ValuehN"`

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

Specifies the path to process image entries to add to the list of exclusions from scheduled
and real-time scanning.

To add values without affecting other existing values, use the following syntax:
`"Path1","Path2",..."PathN"`

To remove values without affecting existing values, use the **Remove-MPPreference** cmdlet:

`Remove-MpPreference -ExclusionProcess "Path1","Path2",..."PathhN"`

To replace all existing values with the values you specify, use the **Set-MpPreference** cmdlet:

`Set-MpPreference -ExclusionProcess "Path1","Path2"..."PathN"`.

Process image entries exclude files opened by executable programs only, not the processes
themselves. To add processes to the list of exclusions, use the **ExclusionPath** parameter.

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

### -ThreatIDDefaultAction_Actions

Use the **ThreatIDDefaultAction_Ids** and **ThreatIDDefaultAction_Actions** parameters
together in the same command to add the actions to take on the corresponding threats.

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

To add values without affecting other existing values, use the following syntax:

`Add-MpPreference -ThreatIDDefaultAction_Ids ThreatID1,ThreatID2,...ThreatIDN -ThreatIDDefaultAction_Actions Action1,Action2,...ActionN`

To remove values without affecting existing values, use the **Remove-MPPreference** cmdlet:

`Remove-MpPreference -ThreatIDDefaultAction_Ids ThreatID1,ThreatID2,...ThreatIDN -ThreatIDDefaultAction_Actions Action1,Action2,...ActionN`

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
Accepted values: Clean, Quarantine, Remove, Allow, UserDefined, NoAction, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThreatIDDefaultAction_Ids

Use the **ThreatIDDefaultAction_Ids** and **ThreatIDDefaultAction_Actions** parameters
together in the same command to add the actions to take on the corresponding threats.

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

To add values without affecting other existing values, use the following syntax:

`Add-MpPreference -ThreatIDDefaultAction_Ids ThreatID1,ThreatID2,...ThreatIDN -ThreatIDDefaultAction_Actions Action1,Action2,...ActionN`

To remove values without affecting existing values, use the **Remove-MpPreference** cmdlet:

`Remove-MpPreference -ThreatIDDefaultAction_Ids ThreatID1,ThreatID2,...ThreatIDN -ThreatIDDefaultAction_Actions Action1,Action2,...ActionN`

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-MpPreference](./Get-MpPreference.md)

[Remove-MpPreference](./Remove-MpPreference.md)

[Set-MpPreference](./Set-MpPreference.md)
