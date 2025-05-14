---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
ms.date: 09/27/2022
online version: https://learn.microsoft.com/powershell/module/clusterawareupdating/set-cauclusterrole?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-CauClusterRole
---

# Set-CauClusterRole

## SYNOPSIS
Sets configuration properties for the CAU clustered role on the specified cluster.

## SYNTAX

### MonthlyDayOfWeek (Default)

```
Set-CauClusterRole [-UseDefault] [-StartDate <DateTime>] [-DaysOfWeek <Weekdays>]
 [-WeeksOfMonth <Int32[]>] [-CauPluginName <String[]>] [-CauPluginArguments <Hashtable[]>]
 [-MaxFailedNodes <Int32>] [-MaxRetriesPerNode <Int32>] [-NodeOrder <String[]>]
 [-PreUpdateScript <String>] [-PostUpdateScript <String>] [-ConfigurationName <String>]
 [-RequireAllNodesOnline] [-WarnAfter <TimeSpan>] [-StopAfter <TimeSpan>]
 [-RebootTimeoutMinutes <Int32>] [-SeparateReboots] [-RunPluginsSerially] [-StopOnPluginFailure]
 [-EnableFirewallRules] [-FailbackMode <FailbackType>] [-SuspendClusterNodeTimeoutMinutes <Int32>]
 [-ForcePauseNoDrain] [-ForcePauseAndDrain] [-ForcePauseDrainAndReboot] [-SkipUpdateChecks]
 [-SiteAwareUpdatingOrder <String[]>] [-OsRollingUpgrade] [-AttemptSoftReboot]
 [-RebootMode <RebootType>] [[-ClusterName] <String>] [[-Credential] <PSCredential>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateNow

```
Set-CauClusterRole [-UpdateNow] [[-ClusterName] <String>] [[-Credential] <PSCredential>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UseDefault

```
Set-CauClusterRole [-UseDefault] [[-ClusterName] <String>] [[-Credential] <PSCredential>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Weekly

```
Set-CauClusterRole [-UseDefault] [-StartDate <DateTime>] [-DaysOfWeek <Weekdays>]
 [-IntervalWeeks <Int32>] [-CauPluginName <String[]>] [-CauPluginArguments <Hashtable[]>]
 [-MaxFailedNodes <Int32>] [-MaxRetriesPerNode <Int32>] [-NodeOrder <String[]>]
 [-PreUpdateScript <String>] [-PostUpdateScript <String>] [-ConfigurationName <String>]
 [-RequireAllNodesOnline] [-WarnAfter <TimeSpan>] [-StopAfter <TimeSpan>]
 [-RebootTimeoutMinutes <Int32>] [-SeparateReboots] [-RunPluginsSerially] [-StopOnPluginFailure]
 [-EnableFirewallRules] [-FailbackMode <FailbackType>] [-SuspendClusterNodeTimeoutMinutes <Int32>]
 [-ForcePauseNoDrain] [-ForcePauseAndDrain] [-ForcePauseDrainAndReboot] [-SkipUpdateChecks]
 [-SiteAwareUpdatingOrder <String[]>] [-OsRollingUpgrade] [-AttemptSoftReboot]
 [-RebootMode <RebootType>] [[-ClusterName] <String>] [[-Credential] <PSCredential>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Once

```
Set-CauClusterRole [-UseDefault] [-RunOnce] [-CauPluginName <String[]>]
 [-CauPluginArguments <Hashtable[]>] [-MaxFailedNodes <Int32>] [-MaxRetriesPerNode <Int32>]
 [-NodeOrder <String[]>] [-PreUpdateScript <String>] [-PostUpdateScript <String>]
 [-ConfigurationName <String>] [-RequireAllNodesOnline] [-WarnAfter <TimeSpan>]
 [-StopAfter <TimeSpan>] [-RebootTimeoutMinutes <Int32>] [-SeparateReboots] [-RunPluginsSerially]
 [-StopOnPluginFailure] [-EnableFirewallRules] [-FailbackMode <FailbackType>]
 [-SuspendClusterNodeTimeoutMinutes <Int32>] [-ForcePauseNoDrain] [-ForcePauseAndDrain]
 [-ForcePauseDrainAndReboot] [-SkipUpdateChecks] [-SiteAwareUpdatingOrder <String[]>]
 [-OsRollingUpgrade] [-AttemptSoftReboot] [-RebootMode <RebootType>] [[-ClusterName] <String>]
 [[-Credential] <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Set-CauClusterRole` cmdlet sets configuration properties for the Cluster-Aware Updating (CAU)
clustered role on the specified cluster. This cmdlet can specify properties such as the updating
schedule and updating run parameters.

To run this cmdlet with the **PostUpdateScript** or **PreUpdateScript** parameters, Windows
PowerShell remoting must be enabled on each node. To do this, use the `Enable-PSRemoting` cmdlet.
In addition, ensure that the **Windows Remote Management - Compatibility Mode (HTTP-In)** firewall
exception is enabled on each node.

## EXAMPLES

### Example 1: Configure settings for a CAU cluster role on the specified cluster on the first and second weeks of the month

```powershell
$parameters = @{
    ClusterName = 'CONTOSO-FC1'
    DaysOfWeek = 'Tuesday'
    WeeksOfMonth = '1,2'
    RebootTimeoutMinutes = '10'
    Force = $true
}
Set-CauClusterRole $parameters
```

This command configures settings for the CAU clustered role on the cluster named **CONTOSO-FC1**. The
CAU clustered role is configured to perform updating runs on Tuesdays on the first and second weeks
of each month. The CAU clustered role allows 10 minutes for the restarting of each node, if a
restart is necessary. If the restart doesn't complete within this time, then the updating run on
that node is marked as failed. Because the command specifies the **Force** parameter, the cmdlet
runs without displaying confirmation prompts.

This example uses splatting to pass parameter values from the `$parameters` variable to the command.
Learn more about [Splatting](/powershell/module/microsoft.powershell.core/about/about_splatting).

### Example 2: Configure settings for a CAU cluster role on the specified cluster on the second week of the month

```powershell
$parameters = @{
    ClusterName = 'CONTOSO-FC1'
    DaysOfWeek = 'Tuesday'
    WeeksOfMonth = '1,2'
    IntervalWeeks = '2'
    RebootTimeoutMinutes = '10'
    PostUpdateScript = 'c:\verifyupdatesinstalled.ps1'
    Force = $true
}
Set-CauClusterRole $parameters
```

```output
Name                                                        Value 
----                                                        ----- 
ResourceGroupName                                           CAUCAUCldy8 
Status                                                      Online 
StartDate                                                   10/14/2011 3:00:00 AM 
PostUpdateScript                                            G:\verifyupdatesinstalled.ps1 
RebootTimeoutMinutes                                        10 
DaysOfWeek                                                  Tuesday 
WeeksInterval                                               2
```

This command configures settings for the CAU clustered role on the cluster named **CONTOSO-FC1**. The
CAU clustered role is configured to perform updating runs on Tuesdays on the second week of each
month. The CAU clustered role allows 10 minutes for the restarting of each node, if a restart is
necessary. If the restart doesn't complete within this time, then the updating run on that node is
marked as failed. The CAU clustered role runs a script after updating completes, just after the
node leaves Maintenance mode. The script is located at the root of drive G: in clustered storage
and is named `verifyupdatesinstalled.ps1`. Because the command specifies the **Force** parameter,
the cmdlet runs without displaying confirmation prompts.

This example uses splatting to pass parameter values from the `$parameters` variable to the command.
Learn more about [Splatting](/powershell/module/microsoft.powershell.core/about/about_splatting).

### Example 3: Initiate an updating run on the specified cluster

```powershell
Set-CauClusterRole -ClusterName "CONTOSO-FC1" -UpdateNow -Force
```

This command causes the CAU clustered role to initiate an updating run immediately on the cluster
named **CONTOSO-FC1**. Because the command specifies the **Force** parameter, the cmdlet runs without
displaying confirmation prompts

### Example 4: Configure settings for a CAU cluster role on the specified cluster

```powershell
$WarnAfter = New-TimeSpan -hour 1 -minute 90 -seconds 10
$StopAfter = New-TimeSpan -hour 2 -minute 90 -seconds 10
$parameters = @{
    ClusterName = 'CONTOSO-FC1'
    WarnAfter = $WarnAfter
    StopAfter = $StopAfter
    StartDate = [DateTime] '1/1/2012'
    Force = $true
}
Set-CauClusterRole @parameters
```

This example configures settings for the CAU clustered role on the cluster named **CONTOSO-FC1**. Time
spans are specified for logging a warning or canceling the updating run if it isn't completed. The
earliest date that an updating run can be triggered is 1/1/2012. Because the command specifies the
**Force** parameter, the cmdlet runs without displaying confirmation prompts.

This example uses splatting to pass parameter values from the `$parameters` variable to the command.
Learn more about [Splatting](/powershell/module/microsoft.powershell.core/about/about_splatting).

## PARAMETERS

### -AttemptSoftReboot

Indicates that the CAU clustered role attempts a Kernel Soft Reboot (KSR) for the failover cluster.

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
Parameter Sets: MonthlyDayOfWeek, Weekly
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CauPluginName

Specifies one or more plug-ins to use when performing scans or updates. You can specify multiple
values separated with commas. The default is the **Microsoft.WindowsUpdatePlugin** plug-in. This plug-in
coordinates the Windows Update Agent software resident on each cluster node, the same software that
is used when updates are downloaded from Windows Update or Microsoft Update, or from a Windows
Server Update Services (WSUS) server. For more information about how plug-ins work with CAU, see
[How CAU Plug-ins Work](/windows-server/failover-clustering/cluster-aware-updating-plug-ins).

```yaml
Type: String[]
Parameter Sets: MonthlyDayOfWeek, Weekly
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterName

Specifies the name of the cluster on which to configure the CAU clustered role. If not specified,
then the current cluster is used. This parameter is only required when this cmdlet isn't run on a
failover cluster node, or this cmdlet is used to reference a failover cluster different from where
the cmdlet is run.

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

Specifies the Windows PowerShell session configuration that defines the session in which scripts,
specified by the **PreUpdateScript** and **PostUpdateScript** parameters, and cmdlets are run, and
can limit the cmdlets that are available to be run. If either a pre-update or post-update script is
specified but a configuration name isn't specified, then the default session configuration that is
built into Windows PowerShell is used.

```yaml
Type: String
Parameter Sets: MonthlyDayOfWeek, Weekly
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
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysOfWeek

Specifies the days of the week on which the task will be triggered.
Multiple values can be specified either separated with commas or as a hexadecimal sum.

- **Sunday:** (0x01)
- **Monday:** (0x02)
- **Tuesday:** (0x04)
- **Wednesday:** (0x08)
- **Thursday:** (0x10)
- **Friday:** (0x20)
- **Saturday:** (0x40)

**Examples:**
- **-DaysOfWeek:** Monday, Wednesday, Friday
- **-DaysOfWeek:** 0x02, 0x08, 0x20
- **-DaysOfWeek:** 0x2A

```yaml
Type: Weekdays
Parameter Sets: MonthlyDayOfWeek, Weekly
Aliases: 
Accepted values: None, Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableFirewallRules

Indicates that this cmdlet enables the **Remote Shutdown** Windows Firewall rule group on each
cluster node, if it isn't already enabled, each time the CAU clustered role performs an Updating
Run. Enabling this rule group permits inbound communication to each cluster node during each
Updating Run that allows CAU to shut down and restart the node remotely. If Windows Firewall is in
use on the cluster nodes and the rule group is not enabled, the updating run will fail. The
**Remote Shutdown** Windows Firewall rule group is not enabled when it will conflict with Group
Policy settings that are configured for Windows Firewall.

```yaml
Type: SwitchParameter
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FailbackMode

Specifies the method used to bring drained workloads back to the node, at the end of updating the
node. Drained workloads are workloads that were previously running on the node, but were moved to
another node. The acceptable values for this parameter are:

- NoFailback
- Immediate
- Policy
 The default value is Immediate.

```yaml
Type: FailbackType
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
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

Indicates that the CAU cluster role forces cluster nodes to pause and drain roles.

A forced drain moves the roles off of the draining node even if the group cannot move.
A group might not be able to move because no other node can host the group or the group is locked.

```yaml
Type: SwitchParameter
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForcePauseDrainAndReboot

Indicates that the CAU cluster role forces cluster nodes to pause, drain roles, and restart.

A forced drain moves the roles off of the draining node even if the group cannot move.
A group might not be able to move because no other node can host the group or the group is locked.

```yaml
Type: SwitchParameter
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForcePauseNoDrain

Indicates that the CAU cluster role forces cluster nodes to pause.
The nodes are not drained.

```yaml
Type: SwitchParameter
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IntervalWeeks

Specifies the interval between weeks when the task will be triggered. An interval of 1 produces a
weekly schedule. An interval of 2 produces an every-other week schedule.

```yaml
Type: Int32
Parameter Sets: Weekly
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxFailedNodes

Specifies the maximum number of nodes on which updating can fail.
If one more than this number of nodes fails, then the Updating Run is stopped.
The range is from 0 through 1 less than the number of cluster nodes.
The default for most clusters is approximately one-third of the number of nodes.

```yaml
Type: Int32
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxRetriesPerNode

Specifies the maximum number of times that the update process, which includes any pre-update and
post-update scripts, is retried per node. The maximum is 64and the default is 3.

```yaml
Type: Int32
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeOrder

Specifies an array of cluster node names in the order that they should be updated.

```yaml
Type: String[]
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
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
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PostUpdateScript

Specifies the path and file name for a Windows PowerShell script to run after updating completes,
just after the node leaves Maintenance mode. The file name extension must be `.ps1` and the total
length of the path plus the file name must be no longer than 260 characters. As a best practice, the
script should be located on a disk in cluster storage, to ensure that it is always accessible to all
the cluster nodes.

```yaml
Type: String
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
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
practice, the script should be located on a disk in cluster storage, to ensure that it is always
accessible to all the cluster nodes.

```yaml
Type: String
Parameter Sets: MonthlyDayOfWeek, Weekly
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
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
Aliases:
Accepted values: ClusProp, FullReboot, SoftReboot, PluginCustomReboot, OrchestratorDefault

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RebootTimeoutMinutes

Specifies the time in minutes that CAU will allow for the restarting of a node. If the restart
doesn't complete within this time, then the updating run on that node is marked as failed.

```yaml
Type: Int32
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequireAllNodesOnline

Indicates that all cluster nodes must be online and reachable before updating begins.

```yaml
Type: SwitchParameter
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunOnce

Specifies that the CAU run should only be performed once, rather than on a recurring schedule. This
can be useful if you only need to perform a one-time update of your cluster nodes.

```yaml
Type: SwitchParameter
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunPluginsSerially

Indicates that CAU scans each cluster node for applicable updates and stage the updates for each
plug-in in the plug-in order passed into the**CauPluginName** parameter, when multiple plug-ins are
used during an updating run.

By default, CAU scans and stages the applicable updates for all plug-ins in parallel. Regardless of
the configuration of this parameter, CAU installs the applicable updates for each plug-in
sequentially.

The parameter is valid only when multiple plug-ins are specified in the **CauPluginName** parameter.
If a single plug-in is specified, a warning appears.

```yaml
Type: SwitchParameter
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SeparateReboots

Indicates that CAU shuts down and restart a cluster node after each plug-in installs updates on the
node, if the installation of an update by a plug-in requires a restart that CAU will shut down and
restart a cluster node after each plug-in installs updates on the node, if the installation of an
update by a plug-in requires a restart

The parameter is valid only when multiple plug-ins are specified in the **CauPluginName** parameter.
If a single plug-in is specified, a warning appears.

```yaml
Type: SwitchParameter
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SiteAwareUpdatingOrder

Specifies the order in which the CAU cluster role updates cluster nodes.

By default, CAU selects the order of nodes to update based on the level of activity.

```yaml
Type: String[]
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipUpdateChecks

Indicates that the CAU cluster role skips update checks.

```yaml
Type: SwitchParameter
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartDate

Specifies the earliest date on which the updating run can be triggered.

```yaml
Type: DateTime
Parameter Sets: MonthlyDayOfWeek, Weekly
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
`01:30:00` represents one hour and thirty minutes. By default, the updating run is allowed an
unlimited amount of time to complete.

If pre-update or post-update scripts are specified, then the entire process of running scripts and
performing updates must be complete within this time limit.

```yaml
Type: TimeSpan
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
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
multiple plug-ins are used during an updating run.

The parameter is valid only when multiple plug-ins are specified for the **CauPluginName** parameter.
If a single plug-in is specified, a warning appears.

```yaml
Type: SwitchParameter
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
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

These retries don't decrement the value of the **MaxRetriesPerNode** parameter set by the user.

The timeout value is per cluster node. So CAU could potentially spend the amount of time specified
for this value for every node in the cluster in the worst case.

```yaml
Type: Int32
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateNow

Instructs the CAU clustered role to immediately initiate an updating run using the configured
settings.

```yaml
Type: SwitchParameter
Parameter Sets: UpdateNow
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseDefault

Indicates that default values are used for all parameters that don't have specified values.

```yaml
Type: SwitchParameter
Parameter Sets: MonthlyDayOfWeek, UseDefault, Weekly, Once
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
Parameter Sets: MonthlyDayOfWeek, Weekly, Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WeeksOfMonth

Specifies the weeks of the month when the Updating Run should be run.
The value 5 represents the last week of the month.

```yaml
Type: Int32[]
Parameter Sets: MonthlyDayOfWeek
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

### -WhatIf

Shows what would happen if the cmdlet runs.
The cmdlet isn't run.

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

### System.Object

## NOTES

## RELATED LINKS

[Add-CauClusterRole](add-cauclusterrole.md)

[Disable-CauClusterRole](disable-cauclusterrole.md)

[Enable-CauClusterRole](enable-cauclusterrole.md)

[Get-CauClusterRole](get-cauclusterrole.md)

[Remove-CauClusterRole](remove-cauclusterrole.md)
