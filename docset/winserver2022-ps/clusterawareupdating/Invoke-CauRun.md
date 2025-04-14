---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
ms.date: 09/27/2022
online version: https://learn.microsoft.com/powershell/module/clusterawareupdating/invoke-caurun?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-CauRun
---

# Invoke-CauRun

## SYNOPSIS
Performs a scan of cluster nodes for applicable updates and installs those updates through an updating run on the specified cluster.

## SYNTAX

### DefaultParamSet (Default)

```
Invoke-CauRun [-MaxFailedNodes <Int32>] [-MaxRetriesPerNode <Int32>] [-NodeOrder <String[]>]
 [-PreUpdateScript <String>] [-PostUpdateScript <String>] [-ConfigurationName <String>]
 [-RequireAllNodesOnline] [-WarnAfter <TimeSpan>] [-StopAfter <TimeSpan>]
 [-RebootTimeoutMinutes <Int32>] [-SeparateReboots] [-EnableFirewallRules]
 [-FailbackMode <FailbackType>] [-SuspendClusterNodeTimeoutMinutes <Int32>] [-Force]
 [-ForcePauseNoDrain] [-ForcePauseAndDrain] [-ForcePauseDrainAndReboot] [-SkipUpdateChecks]
 [-ForceSelfUpdate] [-SiteAwareUpdatingOrder <String[]>] [[-ClusterName] <String>]
 [[-CauPluginName] <String[]>] [[-Credential] <PSCredential>] [-CauPluginArguments <Hashtable[]>] [-RunPluginsSerially] [-StopOnPluginFailure] [-OsRollingUpgrade] [-AttemptSoftReboot]
 [-RebootMode <RebootType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RecoverParamSet

```
Invoke-CauRun [-ForceRecovery] [-Force] [-ForcePauseNoDrain] [-ForcePauseAndDrain]
 [-ForcePauseDrainAndReboot] [-SkipUpdateChecks] [-ForceSelfUpdate] [[-ClusterName] <String>]
 [[-Credential] <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Invoke-CauRun` cmdlet performs a scan of cluster nodes for applicable updates and installs
those updates through an updating run on the specified cluster. The updating run process includes
the following:

- Scanning for and downloading applicable updates on each cluster node.
- Moving currently running clustered roles off each cluster node.
- Installing the updates on each cluster node.
- Restarting cluster nodes if required by the installed updates.
- Moving the clustered roles back to the original nodes.
- The updating run process also includes ensuring that quorum is maintained, checking for additional
  updates that can only be installed after the initial set of updates are installed, and saving a
  report of the actions taken.

To run this cmdlet with the **PostUpdateScript** or **PreUpdateScript** parameter, Windows
PowerShell remoting must be enabled on each node. To do this, run the `Enable-PSRemoting` cmdlet.
In addition, ensure that the **Windows Remote Management - Compatibility Mode (HTTP-In)** firewall
exception is enabled on each node.

## EXAMPLES

### Example 1: Preform a scan and a full updating run on the specified cluster

```powershell
$parameters = @{
    ClusterName = 'CONTOSO-FC1'
    CauPluginName = 'Microsoft.WindowsUpdatePlugin'
    MaxFailedNodes = '1'
    MaxRetriesPerNode = '3'
    RequireAllNodesOnline = $true
    Force = $true
}
Invoke-CauRun @parameters
```

This command performs a scan and a full updating run on the cluster named `CONTOSO-FC1`. This
cmdlet uses the **Microsoft.WindowsUpdatePlugin** plug-in and requires that all cluster nodes be
online before the running this cmdlet. In addition, this cmdlet allows no more than three retries
per node before marking the node as failed, and allows no more than one node to fail before marking
the entire updating run as failed. Because the command specifies the **Force** parameter, the
cmdlet runs without displaying confirmation prompts.

This example uses splatting to pass parameter values from the `$parameters` variable to the command.
Learn more about [Splatting](/powershell/module/microsoft.powershell.core/about/about_splatting).

### Example 2: Preform a scan and a full updating run on the specified cluster using multiple plug-ins

```powershell
$parameters = @{
    ClusterName = 'CONTOSO-FC1'
    CauPluginName = 'Microsoft.WindowsUpdatePlugin',
                    'Microsoft.HotfixPlugin'
    CauPluginArguments = @{ },
                         @{'HotfixRootFolderPath' = '\\CauHotfixSrv\shareName'}
    StopOnPluginFailure = $true
    EnableFirewallRules = $true
    SeparateReboots = $true
    Force = $true
}
Invoke-CauRun @parameters
```

This command performs a scan and a full updating run on the cluster named **CONTOSO-FC1**. This cmdlet
uses the **Microsoft.WindowsUpdatePlugin** plug-in with the default configuration, and the
**Microsoft.HotfixPlugin** plug-in using the hotfix root folder `\\CauHotfixSrv\shareName` and the
default hotfix configuration file. If it isn't already enabled, the **Remote Shutdown** Windows
Firewall rule group is enabled on each cluster node before the updating run. If a failure occurs
during the installation of updates on a node by **Microsoft.WindowsUpdatePlugin**, updates aren't
applied by **Microsoft.HotfixPlugin plug-in**. If the installation of updates by
**Microsoft.WindowsUpdatePlugin** requires a node to restart, the node restarts before
**Microsoft.HotfixPlugin plug-in** installs updates. Because the command specifies the **Force**
parameter, the cmdlet runs without displaying confirmation prompts.

This example uses splatting to pass parameter values from the `$parameters` variable to the command.
Learn more about [Splatting](/powershell/module/microsoft.powershell.core/about/about_splatting).

### Example 3: Recover from a previous updating run that failed on the specified cluster

```powershell
Invoke-CauRun -ClusterName "CONTOSO-FC1"-ForceRecovery -Force
```

This command recovers from a previous updating run that failed and left the cluster in a Locked
state for the cluster named **CONTOSO-FC1**. Because the command specifies the **Force** parameter,
the recovery is performed without confirmation prompts.

## PARAMETERS

### -AttemptSoftReboot

Indicates that command attempts a Kernel Soft Reboot (KSR) for the failover cluster.

KSR bypasses BIOS/firmware initialization.
You can only use KSR for updates that do not require a BIOS/firmware initialization.

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

Specifies one or more plug-ins to use when performing updates. You can specify multiple values
separated with commas. The default is the **Microsoft.WindowsUpdatePlugin** plug-in. This plug-in
coordinates the Windows Update Agent software resident on each cluster node, the same software that
is used when updates are downloaded from Windows Update or Microsoft Update, or from a Windows
Server Update Services (WSUS) server. For more information about how plug-ins work with CAU, see
[How CAU Plug-ins Work](/windows-server/failover-clustering/cluster-aware-updating-plug-ins).

```yaml
Type: String[]
Parameter Sets: DefaultParamSet
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterName

Specifies a cluster for which this cmdlet installs updates.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationName

Specifies the Windows PowerShell session configuration that defines the session in which scripts are
run, specified by **PreUpdateScript** and **PostUpdateScript** parameters, and can limit the cmdlets
that are available to run. If either a pre-update or post-update script is specified but a
configuration name isn't specified, then the default session configuration that is built into
Windows PowerShell is used.

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

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableFirewallRules

Enables the **Remote Shutdown** Windows Firewall rule group on each cluster node, if it isn't
already enabled. If the **EnableFirewallRules** parameter is specified, CAU automatically re-enables
the **Remote Shutdown** rule group each time the CAU clustered role performs an updating run, in
case the rules are disabled manually in the intervening time. Enabling this rule group permits
inbound communication to each cluster node during each updating run that allows CAU to shut down and
restart the node remotely (if the installation of an update requires a restart). If Windows Firewall
is in use on the cluster nodes and the rule group isn't enabled, the updating run will fail. The
**Remote Shutdown** Windows Firewall rule group isn't enabled when it will conflict with Group
Policy settings that are configured for Windows Firewall.

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

### -FailbackMode

Specifies the method used to bring drained workloads back to the node, at the end of updating the
node. Drained workloads are workloads that were previously run on the node, but were moved to
another node. The acceptable values for this parameter are:

- `NoFailback`
- `Immediate`
- `Policy`

The default value is Immediate.

```yaml
Type: FailbackType
Parameter Sets: DefaultParamSet
Aliases: 
Accepted values: NoFailback, Immediate, Policy

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

### -ForcePauseAndDrain

Indicates that the command forces cluster nodes to pause and drain roles.

A forced drain moves the roles off of the draining node even if the group cannot move.
A group might not be able to move because no other node can host the group or the group is locked.

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

### -ForcePauseDrainAndReboot

Indicates that the command forces cluster nodes to pause, drain roles, and restart.

A forced drain moves the roles off of the draining node even if the group cannot move.
A group might not be able to move because no other node can host the group or the group is locked.

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

### -ForcePauseNoDrain

Indicates that the command forces cluster nodes to pause.
The nodes are not drained.

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

### -ForceSelfUpdate

Specifies whether to update the CAU plugin on the local computer before running the update.

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

### -MaxFailedNodes

Specifies the maximum number of nodes on which updating can fail.
If one more than this number of nodes fails, then the updating run is stopped.
The range is from zero (0) through 1 less than the number of cluster nodes.
The default for most clusters is approximately one-third of the number of nodes.

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

### -MaxRetriesPerNode

Specifies the maximum number of times that the update process (including any pre-update and
post-update scripts) is retried per node. The maximum is 64 and the default is 3.

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

### -NodeOrder

Specifies an array of cluster nodes names in the order that they are updated.

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
be .ps1 and the total length of the path plus the file name must be no longer than 260 characters.
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
complete within this time, then the updating run on that node is marked as failed.

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

### -RequireAllNodesOnline

Indicates that all cluster nodes must be online and reachable before the update begins.

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

### -RunPluginsSerially

Indicates that CAU will scan each cluster node for applicable updates and stage the updates for each
plug-in in the plug-in order passed into the **CauPluginName** parameter when multiple plug-ins are
used during an updating run. By default, CAU scans and stages the applicable updates for all
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

### -SeparateReboots

Indicates that CAU will shut down and restart a cluster node after each plug-in installs updates on
the node, if the installation of an update by a plug-in requires a restart when multiple plug-ins
are used during an updating run. By default, during an updating run, all plug-ins complete the
installation of updates on a cluster node before the node restarts one time.

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

### -SiteAwareUpdatingOrder

Specifies the order in which the command updates cluster nodes.

By default, CAU selects the order of nodes to update based on the level of activity.

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

### -SkipUpdateChecks

Indicates that the command skips update checks.

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

### -StopAfter

Specifies the time in minutes after which the updating run is canceled if it hasn't completed. The
time span can be expressed in the standard ways available in Windows PowerShell, for instance,
01:30:00 represents one hour and thirty minutes. By default, the updating run is allowed an
unlimited amount of time to complete.

If pre-update or post-update scripts are specified, then the entire process of running scripts and
performing updates must be complete within this time limit.

```yaml
Type: TimeSpan
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
multiple plug-ins are used during an updating run. By default, a failure by one plug-in doesn't
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

### -SuspendClusterNodeTimeoutMinutes

Specifies the maximum amount of time CAU should wait for the `Suspend-ClusterNode` cmdlet to
succeed if the underlying clustered space is in degraded condition.

If `Suspend-ClusterNode` fails with ERROR_CLUSTER_SPACE_DEGRADED error, CAU will keep retrying for
**SuspendClusterNodeTimeoutMinutes** or suspend the call if the command succeeds.

The retries for this error don't count towards the **MaxRetriesPerNode** parameter set by the user.

The timeout value is per cluster node. So CAU could potentially spend the amount of time specified
for this value for every node in the cluster in the worst case.

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

### -WarnAfter

Specifies the time in minutes after which a warning is logged if the updating run, including any
pre-update and post-update scripts, hasn't completed. By default, no warning is logged, regardless
of the time taken by the updating run.

```yaml
Type: TimeSpan
Parameter Sets: DefaultParamSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
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

### Microsoft.ClusterAwareUpdating.ClusterResult

### Microsoft.ClusterAwareUpdating.NodeResult

### Microsoft.ClusterAwareUpdating.NodeStatusNotification

### Microsoft.ClusterAwareUpdating.UpdateInfo

### Microsoft.ClusterAwareUpdating.UpdateInstallResult

### Microsoft.ClusterAwareUpdating.UpdateStagingResult

## NOTES

## RELATED LINKS

[Add-CauClusterRole](add-cauclusterrole.md)

[Get-CauRun](get-caurun.md)

[Invoke-CauScan](invoke-causcan.md)

[Stop-CauRun](stop-caurun.md)
