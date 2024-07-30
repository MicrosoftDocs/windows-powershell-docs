---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
ms.date: 07/01/2024
online version: https://learn.microsoft.com/powershell/module/clusterawareupdating/invoke-clusterlesscaurun?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-ClusterlessCauRun
---

# Invoke-ClusterlessCauRun

## SYNOPSIS
Performs a Cluster-Aware Updating (CAU) run on a set of nodes that are not associated with a cluster.

## SYNTAX

### DefaultParamSet (Default)

```
Invoke-ClusterlessCauRun [-MaxRetries <Int32>] [-RebootTimeoutMinutes <Int32>]
 [-EnableFirewallRules] [-PreUpdateScript <String>] [-PostUpdateScript <String>]
 [-ConfigurationName <String>] [-Force] [-CauPluginName <String[]>] [-Credential <PSCredential>]
 [-CauPluginArguments <Hashtable[]>] [-RunPluginsSerially] [-StopOnPluginFailure]
 [-OsRollingUpgrade] [-RebootMode <RebootType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RecoverParamSet

```
Invoke-ClusterlessCauRun [-ForceRecovery] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `Invoke-ClusterlessCauRun` cmdlet performs a CAU run on a set of nodes that are not associated
with a cluster. This cmdlet can be used to update standalone servers or groups of servers that are
not part of a cluster.

## EXAMPLES

### Example 1

```powershell
Invoke-ClusterlessCauRun -MaxRetries 3
```

This example performs a CAU run on the specified nodes, with a maximum of 3 retries for each node
that fails to update.

## PARAMETERS

### -CauPluginArguments

Specifies a set of name=value pairs, as arguments, for each updating plug-in to use.

For instance, to specify a Domain argument for one plug-in:

- `@{Domain=Domain.local}`

You can specify multiple pairs in a set separated with semicolons. For instance:

- `@{name1=value1;name2=value2;name3=value3}`

These name=value pairs must be meaningful to the **CauPluginName** parameter that you specify. If
you specify arguments for more than one plug-in, provide the sets of name=value pairs in the order
that you pass values in **CauPluginName**, separated by commas. For instance:

- `@{name1=value1;name2=value2;name3=value3},@{name4=value4;name5=value5}`

For the default **Microsoft.WindowsUpdatePlugin** plug-in, no arguments are needed. The following
arguments are optional:

- **'IncludeRecommendedUpdates'='\<Value\>'**: Boolean value to indicate that recommended updates
  will be applied in addition to important updates on each node. If not specified, the default value
  is False.
- A standard Windows Update Agent query string that specifies criteria used by the Windows Update
  Agent to filter the updates that will be applied to each node. For a name, use **QueryString** and
  for a value, enclose the full query in quotation marks. If not specified, then the
  **Microsoft.WindowsUpdatePlugin** plug-in by default uses the following argument:
- `QueryString="IsInstalled=0 and Type='Software' and IsHidden=0 and IsAssigned=1"`

For more information about query strings for the default **Microsoft.WindowsUpdatePlugin** plug-in
and the criteria such as IsInstalled that can be included in the query strings, see
[IUpdateSearcher::Search method](/windows/win32/api/wuapi/nf-wuapi-iupdatesearcher-search).

For the **Microsoft.HotfixPlugin** plug-in, the following argument is required:

- **HotfixRootFolderPath=\<Path\>**: The UNC path to a hotfix root folder in an SMB share with a
  structure that contains the updates to apply and that contains the hotfix configuration file.

The following arguments are optional for the **Microsoft.HotfixPlugin** plug-in:

- **RequireSmbEncryption=\<Value\>**: Boolean value to indicate that SMB Encryption will be enforced
  for accessing data from the SMB share. If not specified, the default value is False. To ensure the
  integrity of the data accessed from the SMB share, the plug-in requires that the share is enabled
  for either SMB signing or SMB Encryption.
- **DisableAclChecks=\<Value\>**: Boolean value to indicate that the plug-in will check for
  sufficient permissions on the hotfix root folder and the hotfix configuration file. If not
  specified, the default value is False.
- **HotfixInstallerTimeoutMinutes=\<Integer\>**: The length of time in minutes that the plug-in
  allows the hotfix installer process to return. If not specified, the default value is 30 minutes.
- **HotfixConfigFileName=\<name\>**: Name for the hotfix configuration file. If not specified, the
  default name `DefaultHotfixConfig.xml` is used. For more information about required and optional
  arguments for the **Microsoft.HotfixPlugin** plug-in, see
  [How Cluster-Aware Updating plug-ins work](/windows-server/failover-clustering/cluster-aware-updating-plug-ins).

```yaml
Type: Hashtable[]
Parameter Sets: DefaultParamSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CauPluginName

Specifies one or more plug-ins to use when performing scans. You can specify multiple values
separated with commas. The default is the **Microsoft.WindowsUpdatePlugin** plug-in. This plug-in
coordinates the Windows Update Agent software resident on each cluster node, the same software that
is used when updates are downloaded from Windows Update or Microsoft Update, or from a Windows
Server Update Services (WSUS) server. For more information about how plug-ins work with
Cluster-Aware Updating (CAU), see
[How Cluster-Aware Updating plug-ins work](/windows-server/failover-clustering/cluster-aware-updating-plug-ins).

```yaml
Type: String[]
Parameter Sets: DefaultParamSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationName

Specifies the Windows PowerShell session configuration that defines the session in which scripts,
specified by the **PreUpdateScript** and **PostUpdateScript** parameters, and cmdlets are run, and
can limit the cmdlets that are available to be run. If either a pre-update or post-update script is
specified but a configuration name isn't specified, then the default session configuration that is
built into Windows PowerShell is used.

```yaml
Type: String
Parameter Sets: DefaultParamSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies the administrative credentials for the target cluster.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableFirewallRules

Enables the **Remote Shutdown** Windows Firewall rule group on each cluster node, if it isn't
already enabled. If the **EnableFirewallRules** parameter is specified, CAU automatically re-enables
the **Remote Shutdown** rule group each time the CAU clustered role performs an Updating Run, in
case the rules are disabled manually in the intervening time.

Enabling this rule group permits inbound communication to each cluster node during each updating
run that allows CAU to shut down and restart the node remotely (if the installation of an update
requires a restart). If Windows Firewall is in use on the cluster nodes and the rule group isn't
enabled, the Updating Run will fail. The **Remote Shutdown** Windows Firewall rule group isn't
enabled when it will conflict with Group Policy settings that are configured for Windows Firewall.

```yaml
Type: SwitchParameter
Parameter Sets: DefaultParamSet
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
Aliases: f

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceRecovery

Indicates that the cmdlet recovers from a previous failed run that left the cluster in a Locked
state.

This switch defeats the synchronization mechanism used to prevent two update coordinators from
accidentally updating the same cluster at the same time. Use with care.

```yaml
Type: SwitchParameter
Parameter Sets: RecoverParamSet
Aliases: Recover

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxRetries

Specifies the maximum number of times that a node should be retried if an update fails. This can be
useful if you want to ensure that all nodes are updated.

```yaml
Type: Int32
Parameter Sets: DefaultParamSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OsRollingUpgrade

Indicates that the CAU cluster role upgrades the operating system of the cluster nodes without
stopping the Hyper-V or the Scale-Out File Server workloads.

```yaml
Type: SwitchParameter
Parameter Sets: DefaultParamSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PostUpdateScript

Specifies the path and file name for a Windows PowerShell script to run on each node after updating
finishes, and just after the node is brought out of Maintenance mode. The file name extension must
be `.ps1` and the total length of the path plus the file name must be no longer than 260 characters.
As a best practice, the script should be located on a disk in cluster storage, or at a highly
available network share, to ensure that it is always accessible to all the cluster nodes.

```yaml
Type: String
Parameter Sets: DefaultParamSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreUpdateScript

Specifies the path and file name for a Windows PowerShell script to run on each node before updating
begins, and before the node is put into Maintenance mode. The file name extension must be `.ps1` and
the total length of the path plus the file name must be no longer than 260 characters. As a best
practice, the script should be located on a disk in cluster storage, or at a highly available
network share, to ensure that the script is always accessible to all the cluster nodes. If a
pre-update script fails, the node isn't updated.

```yaml
Type: String
Parameter Sets: DefaultParamSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RebootMode

Specifies the type of reboot to use for each node in the cluster during the update. The available
values are:

- `ClusProp`
- `FullReboot`
- `SoftReboot`
- `PluginCustomReboot`
- `OrchestratorDefault`

```yaml
Type: RebootType
Parameter Sets: DefaultParamSet
Aliases:
Accepted values: ClusProp, FullReboot, SoftReboot, PluginCustomReboot, OrchestratorDefault

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RebootTimeoutMinutes

Specifies the time in minutes that CAU allows for the restarting of a node. If the restart doesn't
complete within this time, then the Updating Run on that node will be marked as failed.

```yaml
Type: Int32
Parameter Sets: DefaultParamSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunPluginsSerially

Indicates that CAU will scan each cluster node for applicable updates and stage the updates for each
plug-in in the plug-in order passed into the **CauPluginName** parameter when multiple plug-ins are
used during an Updating Run. By default, CAU scans and stages the applicable updates for all
plug-ins in parallel. Regardless of the configuration of this parameter, CAU installs the applicable
updates for each plug-in sequentially.

The parameter is valid only when multiple plug-ins are specified for the **CauPluginName**
parameter. If a single plug-in is specified, a warning appears.

```yaml
Type: SwitchParameter
Parameter Sets: DefaultParamSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StopOnPluginFailure

Indicates that if a failure occurs during the application of updates on a node by any plug-in,
subsequent updates on the node that are coordinated by the remaining plug-ins are stopped when
multiple plug-ins are used during an Updating Run. By default, a failure by one plug-in doesn't
affect the application of updates on a node by other plug-ins.

The parameter is valid only when multiple plug-ins are specified for the **CauPluginName**
parameter. If a single plug-in is specified, a warning appears.

```yaml
Type: SwitchParameter
Parameter Sets: DefaultParamSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

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
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### None

## OUTPUTS

### Microsoft.ClusterAwareUpdating.ActivityIdMap

### Microsoft.ClusterAwareUpdating.NodeResult

### Microsoft.ClusterAwareUpdating.NodeStatusNotification

### Microsoft.ClusterAwareUpdating.UpdateInfo

### Microsoft.ClusterAwareUpdating.UpdateInstallResult

### Microsoft.ClusterAwareUpdating.UpdateStagingResult

## NOTES

## RELATED LINKS

[Get-ClusterlessCauRun](get-clusterlesscaurun.md)
