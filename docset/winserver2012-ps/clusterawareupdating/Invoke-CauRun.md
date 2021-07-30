---
external help file: ClusterAware_Cmdlets.xml
Module Name: ClusterAwareUpdating
online version: https://docs.microsoft.com/powershell/module/clusterawareupdating/invoke-caurun?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Invoke-CauRun

## SYNOPSIS
Performs a scan of cluster nodes for applicable updates and installs those updates via an Updating Run on the specified cluster.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Invoke-CauRun [[-ClusterName] <String>] [[-CauPluginName] <String[]>] [[-Credential] <PSCredential>]
 [-CauPluginArguments <Hashtable[]>] [-ConfigurationName <String>] [-EnableFirewallRules] [-Force]
 [-MaxFailedNodes <Int32>] [-MaxRetriesPerNode <Int32>] [-NodeOrder <String[]>] [-PostUpdateScript <String>]
 [-PreUpdateScript <String>] [-RebootTimeoutMinutes <Int32>] [-RequireAllNodesOnline] [-RunPluginsSerially]
 [-SeparateReboots] [-StopAfter <TimeSpan>] [-StopOnPluginFailure] [-WarnAfter <TimeSpan>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Invoke-CauRun [[-ClusterName] <String>] [[-Credential] <PSCredential>] [-Force] [-ForceRecovery] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Invoke-CauRun** cmdlet performs a scan of cluster nodes for applicable updates and installs those updates via an Updating Run on the specified cluster.
The Updating Run process includes the following: 

 - Scanning for and downloading applicable updates on each cluster node. 

 - Moving currently running clustered roles off each cluster node. 

 - Installing the updates on each cluster node. 

 - Restarting cluster nodes if required by the installed updates. 

 - Moving the clustered roles back to the original nodes. 

The Updating Run process also includes ensuring that quorum is maintained, checking for additional updates that can only be installed after the initial set of updates are installed, and saving a report of the actions taken.

Note: To run this cmdlet with the **PostUpdateScript** or **PreUpdateScript** parameter, Windows PowerShell® remoting must be enabled on each node.
To do this, run the Enable-PSRemotinghttps://go.microsoft.com/fwlink/p/?LinkID=144300 cmdlet.
In addition, ensure that the Windows Remote Management - Compatibility Mode (HTTP-In) firewall exception is enabled on each node.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Invoke-CauRun -ClusterName CONTOSO-FC1 -CauPluginName Microsoft.WindowsUpdatePlugin -MaxFailedNodes -1 -MaxRetriesPerNode 3 -RequireAllNodesOnline -Force
```

This example performs a scan and a full Updating Run on the cluster named CONTOSO-FC1.
This cmdlet uses the Microsoft.WindowsUpdatePlugin plug-in and requires that all cluster nodes be online before the running this cmdlet.
In addition, this cmdlet allows no more than three retries per node before marking the node as failed, and allows no more than one node to fail before marking the entire Updating Run as failed.
This cmdlet is performed without confirmation prompts.

### EXAMPLE 2
```
PS C:\> Invoke-CauRun -ClusterName CONTOSO-FC1 -CauPluginName Microsoft.WindowsUpdatePlugin, Microsoft.HotfixPlugin -CauPluginArguments @{ }, @{ 'HotfixRootFolderPath' = '\\CauHotfixSrv\shareName' } -EnableFirewallRules -StopOnPluginFailure -SeparateReboots -Force
```

This example performs a scan and a full Updating Run on the cluster named CONTOSO-FC1.
This cmdlet uses the Microsoft.WindowsUpdatePlugin plug-in with the default configuration, and the Microsoft.HotfixPlugin plug-in using the hotfix root folder \\\\CauHotfixSrv\shareName and the default hotfix configuration file.
If it is not already enabled, the **Remote Shutdown** Windows Firewall rule group is enabled on each cluster node before the Updating Run.
If a failure occurs during the installation of updates on a node by **Microsoft.WindowsUpdatePlugin**, updates will not be applied by **Microsoft.HotfixPlugin plug-in**.
If the installation of updates by **Microsoft.WindowsUpdatePlugin** requires a node to restart, the node will restart before **Microsoft.HotfixPlugin plug-in** installs updates.
The cmdlet runs without displaying confirmation prompts.

### EXAMPLE 3
```
PS C:\> Invoke-CauRun -ClusterName CONTOSO-FC1 -ForceRecovery -Force
```

This example recovers from a previous Updating Run that failed and left the cluster in a Locked state for the cluster named CONTOSO-FC1.
The recovery is performed without confirmation prompts.

## PARAMETERS

### -CauPluginArguments
Passes a set of name=value pairs (arguments) for each updating plug-in to use.
For example, to specify a Domain argument for one plug-in: 

 - `@{Domain=Domain.local}`

You can specify multiple pairs in a set separated with semicolons.
For example: 

 - `@{name1=value1;name2=value2;name3=value3}`

These name=value pairs must be meaningful to the **CauPluginName** that you specify. 

If you specify arguments for more than one plug-in, provide the sets of name=value pairs in the order that you pass values in **CauPluginName**, separated by commas.
For example: 

 - `@{name1=value1;name2=value2;name3=value3},@{name4=value4;name5=value5}`


For the default **Microsoft.WindowsUpdatePlugin** plug-in, no arguments are needed.
The following arguments are optional: 

 - **'IncludeRecommendedUpdates'='\<Value\>'**: Boolean value to indicate that recommended updates will be applied in addition to important updates on each node.
If not specified, the default value is **'False'**. 

 - A standard Windows Update Agent query string that specifies criteria used by the Windows Update Agent to filter the updates that will be applied to each node.
For a name, use **QueryString** and for a value, enclose the full query in quotation marks. 

If not specified, then the **Microsoft.WindowsUpdatePlugin** plug-in by default uses the following argument: 

 - `QueryString="IsInstalled=0 and Type='Software' and IsHidden=0 and IsAssigned=1"`

For more information about query strings for the default **Microsoft.WindowsUpdatePlugin** plug-in and the criteria such as IsInstalled that can be included in the query strings, see the topic about search criteria in the Windows Update Agent (WUA) API Referencehttps://go.microsoft.com/fwlink/p/?LinkId=223304. 


For the **Microsoft.HotfixPlugin** plug-in, the following argument is required: 

 - **HotfixRootFolderPath**: The UNC path to a hotfix root folder in an SMB share with a structure that contains the updates to apply and that contains the hotfix configuration file


The following arguments are optional for the **Microsoft.HotfixPlugin** plug-in: 

 - **RequireSmbEncryption=\<Value\>**: Boolean value to indicate that SMB Encryption will be enforced for accessing data from the SMB share.
If not specified, the default value is **'False'**.
To ensure the integrity of the data accessed from the SMB share, the plug-in requires that the share is enabled for either SMB signing or SMB Encryption. 

 - **DisableAclChecks=\<Value\>**: Boolean value to indicate that the plug-in will check for sufficient permissions on the hotfix root folder and the hotfix configuration file.
If not specified, the default value is **'False'**.

 - **HotfixInstallerTimeoutMinutes=\<Integer\>**: The length of time in minutes that the plug-in allows the hotfix installer process to return.
If not specified, the default value is 30 minutes.

 - **HotfixConfigFileName=\<name\>**: Name for the hotfix configuration file.
If not specified, the default name DefaultHotfixConfig.xml is used. 

For more information about required and optional arguments for the **Microsoft.HotfixPlugin** plug-in, see the content about Cluster-Aware Updating plug-inshttps://go.microsoft.com/fwlink/p/?LinkId=235333.

```yaml
Type: Hashtable[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CauPluginName
Specifies one or more plug-ins to use when performing updates.
You can specify multiple values separated with commas.
The default is the Microsoft.WindowsUpdatePlugin plug-in.
This plug-in coordinates the Windows Update Agent software resident on each cluster node, the same software that is used when updates are downloaded from Windows Update or Microsoft Update, or from a Windows Server Update Services (WSUS) server.
For more information about how plug-ins work with CAU, see the content about Cluster-Aware Updating plug-inshttps://go.microsoft.com/fwlink/p/?LinkId=235333.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterName
Specifies the name of the cluster on which to install updates.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationName
Specifies the Windows PowerShell session configuration that defines the session in which scripts (specified by **PreUpdateScript** and **PostUpdateScript**) and cmdlets are run, and can limit the cmdlets that are available to be run.
If either a pre-update or post-update script is specified but a configuration name is not specified, then the default session configuration that is built into Windows PowerShell ("Microsoft.PowerShell") is used.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableFirewallRules
Enables the **Remote Shutdown** Windows Firewall rule group on each cluster node, if it is not already enabled.
If the **EnableFirewallRules** parameter is specified, CAU will also automatically re-enable the **Remote Shutdown** rule group each time the CAU clustered role performs an Updating Run, in case the rules are disabled manually in the intervening time.
Enabling this rule group permits inbound communication to each cluster node during each Updating Run that allows CAU to shut down and restart the node remotely (if the installation of an update requires a restart).
If Windows Firewall is in use on the cluster nodes and the rule group is not enabled, the Updating Run will fail.
The **Remote Shutdown** Windows Firewall rule group is not enabled when it will conflict with Group Policy settings that are configured for Windows Firewall.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Runs the cmdlet without prompting for confirmation.
By default the cmdlet will ask for confirmation from the user before proceeding.

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
Recovers from a previous failed run that left the cluster in a Locked state. 
Note: This switch defeats the synchronization mechanism used to prevent two update coordinators from accidentally trying to update the same cluster at the same time.
Use with care.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxFailedNodes
Specifies the maximum number of nodes on which updating can fail.
If one more than this number of nodes fails, then the Updating Run is stopped.
The range is from zero (`0`) through 1 less than the number of cluster nodes.
The default for most clusters is approximately one-third of the number of nodes.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxRetriesPerNode
Specifies the maximum number of times that the update process (including any pre-update and post-update scripts) will be retried per node.
The maximum is `64` and the default is `3`.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeOrder
Specifies the names of the cluster nodes in the order that they should be updated.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PostUpdateScript
Specifies the path and file name for a Windows PowerShell script to run on each node after updating finishes, and just after the node is brought out of **Maintenance** mode.
The file name extension must be `.ps1` and the total length of the path plus the file name must be no longer than 260 characters.
As a best practice, the script should be located on a disk in cluster storage, or at a highly available network share, to ensure that it is always accessible to all of the cluster nodes.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreUpdateScript
Specifies the path and file name for a Windows PowerShell script to run on each node before updating begins, and before the node is put into **Maintenance** mode.
The file name extension must be `.ps1` and the total length of the path plus the file name must be no longer than 260 characters.
As a best practice, the script should be located on a disk in cluster storage, or at a highly available network share, to ensure that the script is always accessible to all of the cluster nodes.
If a pre-update script fails, the node is not updated.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RebootTimeoutMinutes
Specifies the time in minutes that CAU will allow for the restarting of a node (if a restart is necessary).
If the restart does not complete within this time, then the Updating Run on that node will be marked as failed.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: 15
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequireAllNodesOnline
Specifies that all cluster nodes must be online and reachable before updating begins.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunPluginsSerially
When multiple plug-ins are used during an Updating Run, specifies that CAU will scan each cluster node for applicable updates and stage the updates for each plug-in in the plug-in order passed in **CauPluginName**.
By default, CAU scans and stages the applicable updates for all plug-ins in parallel.
Regardless of the configuration of this parameter, CAU installs the applicable updates for each plug-in sequentially. 
**Note:** The parameter is valid only when multiple plug-ins are specified in **CauPluginName**.
If a single plug-in is specified, a warning appears.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SeparateReboots
When multiple plug-ins are used during an Updating Run, specifies that CAU will shut down and restart a cluster node after each plug-in installs updates on the node, if the installation of an update by a plug-in requires a restart.
By default, during an Updating Run, all plug-ins complete the installation of updates on a cluster node before the node restarts one time (if a restart is necessary). 
**Note:** The parameter is valid only when multiple plug-ins are specified in **CauPluginName**.
If a single plug-in is specified, a warning appears.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StopAfter
Specifies the time in minutes after which the Updating Run will be canceled if it has not completed.
The time span can be expressed in the standard ways available in Windows PowerShell, for example, `01:30:00` represents one hour and thirty minutes.
By default, the Updating Run is allowed an unlimited amount of time to complete. 
**Note:** If pre-update or post-update scripts are specified, then the entire process of running scripts and performing updates must be complete within this time limit.

```yaml
Type: TimeSpan
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StopOnPluginFailure
When multiple plug-ins are used during an Updating Run, specifies that if a failure occurs during the application of updates on a node by any plug-in, subsequent updates on the node that are coordinated by the remaining plug-ins are stopped.
By default, a failure by one plug-in does not affect the application of updates on a node by other plug-ins. 
**Note:** The parameter is valid only when multiple plug-ins are specified in **CauPluginName**.
If a single plug-in is specified, a warning appears.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WarnAfter
Specifies the time in minutes after which a warning will be logged if the Updating Run (including any pre-update and post-update scripts) has not completed.
By default, no warning will be logged, regardless of the time taken by the Updating Run.

```yaml
Type: TimeSpan
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

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

[Add-CauClusterRole](./Add-CauClusterRole.md)

[Get-CauRun](./Get-CauRun.md)

[Stop-CauRun](./Stop-CauRun.md)

