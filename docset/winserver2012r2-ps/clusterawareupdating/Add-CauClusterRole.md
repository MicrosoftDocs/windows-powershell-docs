---
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
online version: 
schema: 2.0.0
title: Add-CauClusterRole
ms.author: v-anbarr
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: F8E207A2-77D2-48D8-A689-6B22060C3827
---

# Add-CauClusterRole

## SYNOPSIS
Adds the Cluster-Aware Updating (CAU) clustered role that provides the self-updating functionality to the specified cluster.

## SYNTAX

### MonthlyDayOfWeek (Default)
```
Add-CauClusterRole [-VirtualComputerObjectName <String>] [-GroupName <String>] [-StartDate <DateTime>]
 [-DaysOfWeek <Weekdays>] [-WeeksOfMonth <Int32[]>] [-CauPluginName <String[]>]
 [-CauPluginArguments <Hashtable[]>] [-MaxFailedNodes <Int32>] [-MaxRetriesPerNode <Int32>]
 [-NodeOrder <String[]>] [-PreUpdateScript <String>] [-PostUpdateScript <String>] [-ConfigurationName <String>]
 [-RequireAllNodesOnline] [-WarnAfter <TimeSpan>] [-StopAfter <TimeSpan>] [-RebootTimeoutMinutes <Int32>]
 [-SeparateReboots] [-RunPluginsSerially] [-StopOnPluginFailure] [-EnableFirewallRules]
 [-FailbackMode <FailbackType>] [[-ClusterName] <String>] [[-Credential] <PSCredential>] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Weekly
```
Add-CauClusterRole [-VirtualComputerObjectName <String>] [-GroupName <String>] [-StartDate <DateTime>]
 [-DaysOfWeek <Weekdays>] [-IntervalWeeks <Int32>] [-CauPluginName <String[]>]
 [-CauPluginArguments <Hashtable[]>] [-MaxFailedNodes <Int32>] [-MaxRetriesPerNode <Int32>]
 [-NodeOrder <String[]>] [-PreUpdateScript <String>] [-PostUpdateScript <String>] [-ConfigurationName <String>]
 [-RequireAllNodesOnline] [-WarnAfter <TimeSpan>] [-StopAfter <TimeSpan>] [-RebootTimeoutMinutes <Int32>]
 [-SeparateReboots] [-RunPluginsSerially] [-StopOnPluginFailure] [-EnableFirewallRules]
 [-FailbackMode <FailbackType>] [[-ClusterName] <String>] [[-Credential] <PSCredential>] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-CauClusterRole** cmdlet adds the Cluster-Aware Updating (CAU) clustered role that provides the self-updating functionality to the specified cluster.
When the CAU clustered role has been added to a cluster, the failover cluster can update itself on the schedule that is specified by the user, without requiring an external computer to coordinate the cluster updating process.

Note: To run this cmdlet, Windows PowerShell® remoting must be enabled on each node.
To do this, run the Enable-PSRemotinghttp://go.microsoft.com/fwlink/p/?LinkID=144300 cmdlet.
In addition, ensure that the Windows Remote Management - Compatibility Mode (HTTP-In) firewall exception is enabled on each node.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Add-CauClusterRole -ClusterName CONTOSO-FC1 -DaysOfWeek Tuesday,Saturday -WeeksOfMonth 2,4 -MaxFailedNodes 2 -MaxRetriesPerNode 2 -PostUpdateScript \\CONTOSOFileShare\scripts\verifyupdatesinstalled.ps1 -RequireAllNodesOnline -EnableFirewallRules -Force
```

This example adds the CAU clustered role, using a default name, on the cluster called CONTOSO-FC1.
The CAU clustered role is configured to perform Updating Runs on Tuesdays and Saturdays on the second and fourth weeks of each month.
In an Updating Run, the maximum number of failed nodes is two and the maximum number of retries per node is two.
A script called verifyupdatesinstalled.ps1 runs on each node after it has been fully updated.
Before an Updating Run can begin, all the nodes of that cluster must be running.
If it is not already enabled, the **Remote Shutdown** Windows Firewall rule group will be enabled on each cluster node.
The cmdlet runs without displaying confirmation prompts.

### EXAMPLE 2
```
PS C:\> Add-CauClusterRole -ClusterName CONTOSO-FC1 -DaysOfWeek Tuesday,Saturday -WeeksInterval 3 -MaxFailedNodes 2 -MaxRetriesPerNode 2 -EnableFirewallRules -Force
```

This example adds the CAU clustered role, using a default name, on the cluster called CONTOSO-FC1.
The CAU clustered role is configured to perform Updating Runs on Tuesdays and Saturdays at an interval of every three weeks.
In an Updating Run, the maximum number of failed nodes is two and the maximum number of retries per node is two.
Updating Runs can begin even when the nodes of the cluster are not all running (as long as the cluster itself has quorum and is running).
If it is not already enabled, the **Remote Shutdown** Windows Firewall rule group will be enabled on each cluster node.
The cmdlet runs without displaying confirmation prompts.

### EXAMPLE 3
```
PS C:\> Add-CauClusterRole -ClusterName CONTOSO-FC1 -CauPluginName Microsoft.WindowsUpdatePlugin, Microsoft.HotfixPlugin -CauPluginArguments @{ 'IncludeRecommendedUpdates' = 'True' }, @{ 'HotfixRootFolderPath' = '\\CauHotfixSrv\shareName' } -StopOnPluginFailure -EnableFirewallRules -Force
```

This example adds the CAU clustered role, using a default name, on the cluster called CONTOSO-FC1.
The CAU clustered role is configured to perform updates using the **Microsoft.WindowsUpdatePlugin** plug-in with the optional **'IncludeRecommendedUpdates'** parameter set to **'True'**, and using the **Microsoft.HotfixPlugin plug-in** using the hotfix root folder \\\\CauHotfixSrv\shareName and the default hotfix configuration file.
If a failure occurs during the installation of updates on a node by **Microsoft.WindowsUpdatePlugin**, updates will not be applied by **Microsoft.HotfixPlugin plug-in**.
If it is not already enabled, the **Remote Shutdown** Windows Firewall rule group will be enabled on each cluster node.
The cmdlet runs without displaying confirmation prompts.

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
                         
 For more information about query strings for the default **Microsoft.WindowsUpdatePlugin** plug-in and the criteria such as IsInstalled that can be included in the query strings, see the topic about search criteria in the Windows Update Agent (WUA) API Referencehttp://go.microsoft.com/fwlink/p/?LinkId=223304. 

                         
For the **Microsoft.HotfixPlugin** plug-in.
the following argument is required: 
                         
 - **HotfixRootFolderPath=\<Path\>**: The UNC path to a hotfix root folder in an SMB share with a structure that contains the updates to apply and that contains the hotfix configuration file

                         
The following arguments are optional for the **Microsoft.HotfixPlugin** plug-in: 
                         
 - **RequireSmbEncryption=\<Value\>**: Boolean value to indicate that SMB Encryption will be enforced for accessing data from the SMB share.
If not specified, the default value is **'False'**.
To ensure the integrity of the data accessed from the SMB share, the plug-in requires that the share is enabled for either SMB signing or SMB Encryption. 
                         
 - **DisableAclChecks=\<Value\>**: Boolean value to indicate that the plug-in will check for sufficient permissions on the hotfix root folder and the hotfix configuration file.
If not specified, the default value is **'False'**. 
                         
 - **HotfixInstallerTimeoutMinutes=\<Integer\>**: The length of time in minutes that the plug-in allows the hotfix installer process to return.
If not specified, the default value is 30 minutes. 
                         
 - **HotfixConfigFileName=\<name\>**: Name for the hotfix configuration file.
If not specified, the default name DefaultHotfixConfigFile.xml is used. 
                         
For more information about required and optional arguments for the **Microsoft.HotfixPlugin** plug-in, see the content about Cluster-Aware Updating plug-inshttp://go.microsoft.com/fwlink/p/?LinkId=235333.

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CauPluginName
Specifies one or more plug-ins to use when performing scans or updates.
You can specify multiple values separated with commas.
The default is the Microsoft.WindowsUpdatePlugin plug-in.
This plug-in coordinates the Windows Update Agent software resident on each cluster node, the same software that is used when updates are downloaded from Windows Update or Microsoft Update, or from a Windows Server Update Services (WSUS) server.
For more information about how plug-ins work with CAU, see the content about Cluster-Aware Updating plug-inshttp://go.microsoft.com/fwlink/p/?LinkId=235333.

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

### -ClusterName
Specifies the name of the cluster on which to create the CAU clustered role.
This parameter is only required when this cmdlet is not run on a failover cluster node, or this cmdlet is used to reference a failover cluster different from where the cmdlet is run.

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
Specifies the Windows PowerShell session configuration that defines the session in which scripts (specified by **PreUpdateScript** and **PostUpdateScript**) and cmdlets are run, and can limit the cmdlets that are available to be run.
If either a pre-update or post-update script is specified but a configuration name is not specified, then the default session configuration that is built into Windows PowerShell® ("Microsoft.PowerShell") is used.

```yaml
Type: String
Parameter Sets: (All)
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
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysOfWeek
Specifies the days of the week on which the updating task will be triggered.
Multiple values can be specified either separated with commas or as a hexadecimal sum. 
                         
 - **Sunday:** (0x01) 
                         
 - **Monday:** (0x02) 
                         
 - **Tuesday:** (0x04) 
                         
 - **Wednesday:** (0x08) 
                         
 - **Thursday:** (0x10) 
                         
 - **Friday:** (0x20) 
                         
 - **Saturday:** (0x40) 
**Examples:**
                         
 - **-DaysOfWeek: **Monday, Wednesday, Friday 
                         
 - **-DaysOfWeek:** 0x02, 0x08, 0x20 
                         
 - **-DaysOfWeek:** 0x2A

```yaml
Type: Weekdays
Parameter Sets: (All)
Aliases: 
Accepted values: None, Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: False
Position: Named
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FailbackMode
Specifies the method used to bring drained workloads back to the node, at the end of updating the node.
Drained workloads are workloads that were previously running on the node, but were moved to another node.
The acceptable values for this parameter are:NoFailback, Immediate, and Policy.
The default value is Immediate.

```yaml
Type: FailbackType
Parameter Sets: (All)
Aliases: 
Accepted values: NoFailback, Immediate, Policy

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
Aliases: f

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupName
The NetBIOS name of the resource group for the CAU clustered role.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IntervalWeeks
Specifies the interval between weeks when the task will be triggered.
An interval of `1` produces a weekly schedule.
An interval of `2` produces an every-other week schedule.

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
The range is from zero (`0`) through 1 less than the number of cluster nodes.
The default for most clusters is approximately one-third of the number of nodes.

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

### -MaxRetriesPerNode
Specifies the maximum number of times that the update process (including any pre-update and post-update scripts) will be retried per node.
The maximum is `64` and the default is `3`.

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

### -NodeOrder
Specifies the names of the cluster nodes in the order that they should be updated.

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

### -PostUpdateScript
Specifies the path and file name for a Windows PowerShell script to run on each node after updating finishes, and just after the node is brought out of **Maintenance** mode.
The file name extension must be .ps1 and the total length of the path plus the file name must be no longer than 260 characters.
As a best practice, the script should be located on a disk in cluster storage, or at a highly available network share, to ensure that the script is always accessible to all of the cluster nodes.

```yaml
Type: String
Parameter Sets: (All)
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
Parameter Sets: (All)
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
Parameter Sets: (All)
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
Parameter Sets: (All)
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
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartDate
Specifies the earliest date on which the Updating Run can be triggered.

```yaml
Type: DateTime
Parameter Sets: (All)
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
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualComputerObjectName
Specifies the name of a prestaged virtual computer object that is used by the CAU clustered role.
For more information, see the Steps to create computer objects in Active Directoryhttp://go.microsoft.com/fwlink/p/?LinkId=237624.
If not specified, then a virtual computer object is created using a generated name.
Generating a name automatically requires the cluster name object to have permissions to create the virtual computer object in Active Directory.

```yaml
Type: String
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WeeksOfMonth
Specifies the weeks of the month when the Updating Run should be run.
The value `5` represents the last week of the month.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Disable-CauClusterRole](./Disable-CauClusterRole.md)

[Enable-CauClusterRole](./Enable-CauClusterRole.md)

[Get-CauClusterRole](./Get-CauClusterRole.md)

[Remove-CauClusterRole](./Remove-CauClusterRole.md)

[Set-CauClusterRole](./Set-CauClusterRole.md)

