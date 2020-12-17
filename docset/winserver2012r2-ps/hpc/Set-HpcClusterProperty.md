---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Set-HpcClusterProperty
description:
keywords: powershell, cmdlet
ms.date: 12/20/2016
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: http://go.microsoft.com/fwlink/?LinkId=182659
schema: 2.0.0
ms.assetid: B0D29FB7-E5E3-466A-8247-05A7151F1734
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-HpcClusterProperty

## SYNOPSIS
Sets cluster-wide properties.

## SYNTAX

### environment (Default)
```
Set-HpcClusterProperty -Environment <String[]> [-Scheduler <String[]>]
 [<CommonParameters>]
```

### parameter
```
Set-HpcClusterProperty [-AllowNewUserConnections <Boolean>] [-InactivityCount <Int32>]
 [-InactivityCountAzure <Int32>] [-HeartbeatInterval <Int32>] [-PreemptionType <PreemptionMode>]
 [-AffinityType <AffinityMode>] [-SchedulingMode <SchedulingMode>] [-HpcSoftCard <HpcSoftCardPolicy>]
 [-HpcSoftCardTemplate <String>] [-SoftCardExpirationWarning <Int32>] [-SubmissionFilterProgram <String>]
 [-SubmissionFilterTimeout <Int32>] [-ActivationFilterProgram <String>] [-ActivationFilterTimeout <Int32>]
 [-TtlCompletedJobs <Int32>] [-JobRetryCount <Int32>] [-TaskRetryCount <Int32>] [-BackfillLookAhead <Int32>]
 [-AutomaticGrowthEnabled <Boolean>] [-AutomaticShrinkEnabled <Boolean>] [-JobCleanUpHour <Int32>]
 [-NodeReleaseTaskTimeout <Int32>] [-TaskCancelGracePeriod <Int32>] [-DefaultHoldDuration <Int32>]
 [-PriorityBias <PriorityBias>] [-ReBalancingInterval <Int32>] [-ExcludedNodesLimit <Int32>]
 [-EmailNotificationEnabled <Boolean>] [-EmailFromAddress <String>] [-EmailSmtpServer <String>]
 [-EmailUseSsl <Boolean>] [-TtlCompletedRuns <String>] [-RunCleanUpHour <String>]
 [-ConcurrencyTestRunNumber <String>] [-EnablePools <Boolean>] [-GrowByPreemptionEnabled <Boolean>]
 [-TaskImmediatePreemptionEnabled <Boolean>] [-BackfillLoadPeriod <Int32>] [-DisableCredentialReuse <Boolean>]
 [-NettcpOver443 <Boolean>] [-PreemptionBalancedMode <String>] [-GetAzureBatchTaskOutput <Boolean>]
 [-AzureLogsToBlob <String>] [-AzureLogsToBlobThrottling <Int32>] [-AzureLogsToBlobInterval <Int32>] [-Scheduler <String[]>] [<CommonParameters>]
```

### installCredential
```
Set-HpcClusterProperty [-InstallCredential <PSCredential>] [-Scheduler <String[]>] [<CommonParameters>]
```

### emailCredential
```
Set-HpcClusterProperty [-EmailCredential <PSCredential>] [-Scheduler <String[]>] [<CommonParameters>]
```

### nodeNameSeries
```
Set-HpcClusterProperty [-NodeNamingSeries <String>] [-Scheduler <String[]>] [<CommonParameters>]
```

### nodeNameSequence
```
Set-HpcClusterProperty [-NodeNamingSequenceCount <Int32>] [-Scheduler <String[]>] [<CommonParameters>]
```

### collectCounters
```
Set-HpcClusterProperty [-CollectCounters <Boolean>] [-Scheduler <String[]>] [<CommonParameters>]
```

### azureCollectionInterval
```
Set-HpcClusterProperty [-AzureCollectionInterval <Int32>] [-Scheduler <String[]>] [<CommonParameters>]
```

### operationArchive
```
Set-HpcClusterProperty [-OperationArchive <Int32>] [-Scheduler <String[]>] [<CommonParameters>]
```

### operationRetention
```
Set-HpcClusterProperty [-OperationRetention <Int32>] [-Scheduler <String[]>] [<CommonParameters>]
```

### wdsMode
```
Set-HpcClusterProperty [-WDSMode <WdsMode>] [-Scheduler <String[]>]
 [<CommonParameters>]
```

### PerfCounterRetention
```
Set-HpcClusterProperty [-MinuteCounterRetention <Int32>] [-HourCounterRetention <Int32>]
 [-DayCounterRetention <Int32>] [-Scheduler <String[]>]
 [<CommonParameters>]
```

### azureStorageConnectionString
```
Set-HpcClusterProperty [-AzureStorageConnectionString <String>] [-Scheduler <String[]>] [<CommonParameters>]
```

### azureMetricsCollectionEnabled
```
Set-HpcClusterProperty [-AzureMetricsCollectionEnabled <Boolean>] [-Scheduler <String[]>] [<CommonParameters>]
```

### azureIaaSMetricsCollectionEnabled
```
Set-HpcClusterProperty [-AzureIaaSMetricsCollectionEnabled <Boolean>] [-Scheduler <String[]>] [<CommonParameters>]
```

### azureMetricsJobStatisticsDelayMinutes
```
Set-HpcClusterProperty [-AzureMetricsJobStatisticsDelayMinutes <Int32>] [-Scheduler <String[]>] [<CommonParameters>]
```

### autogrowshrink
```
Set-HpcClusterProperty [-EnableGrowShrink <Boolean>] [-TasksPerResourceUnit <Int32>] [-GrowThreshold <Int32>]
 [-GrowInterval <Int32>] [-ShrinkInterval <Int32>] [-ShrinkIdleTimes <Int32>] [-ExtraNodesGrowRatio <Int32>]
 [-GrowByMin <Boolean>] [-SoaJobGrowThreshold <Int32>] [-SoaRequestsPerCore <Int32>]
 [-ExcludeNodeGroups <String[]>] [-Scheduler <String[]>] [<CommonParameters>]
```

### dataExtensibilityEnabled
```
Set-HpcClusterProperty [-DataExtensibilityEnabled <Boolean>] [-Scheduler <String[]>] [<CommonParameters>]
```

### dataExtensibilityTtl
```
Set-HpcClusterProperty [-DataExtensibilityTtl <Int32>] [-Scheduler <String[]>] [<CommonParameters>]
```

### allocationHistoryTtl
```
Set-HpcClusterProperty [-AllocationHistoryTtl <Int32>] [-Scheduler <String[]>] [<CommonParameters>]
```

### restoreMode
```
Set-HpcClusterProperty [-RestoreMode] [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HpcClusterProperty** cmdlet sets the specified cluster-wide properties.
Cluster-wide properties include parameters, environment variables, installation credentials, credentials to use for sending email notifications, the naming series for new compute nodes, and the Windows Deployment Services (DS) mode.

## EXAMPLES

### Example 1: Set the installation credential
```
PS C:\>Set-HpcClusterProperty -InstallCredential CONTOSO\pfuller
```

This command sets the credential that is used to install compute nodes and run diagnostics tasks.

### Example 2: Set the node naming series
```
PS C:\>Set-HpcClusterProperty -NodeNamingSeries "MyCluster%1000%"
```

This command sets the naming series that is used to name new compute nodes added to the HPC cluster in the future.
The naming series in this example generates compute node names like MyCluster1000, MyCluster1001, and so on.

### Example 3: Set an environment variable
```
PS C:\>Set-HpcClusterProperty -Environment "CCP_CLUSTER_NAME=mycluster"
```

This command sets a cluster-wide environment variable named CCP_CLUSTER_NAME to mycluster.

### Example 4: Set the heart beat interval
```
PS C:\>Set-HpcClusterProperty -HeartbeatInterval 40
```

This command sets the cluster-wide parameter *HeartbeatInterval* to 40.
This value means that the job scheduler will send a health probe to the HPC Node Manager Service every 40 seconds.

### Example 5: Set diagnostic test run parameters
```
PS C:\>Set-HpcClusterProperty -TtlCompletedRuns 6 -RunCleanupHour 4
```

This command sets the cluster-wide parameters named TtlCompletedRuns and RunCleanupHour to 6 and 4, respectively.
As a result, information about completed diagnostic test runs are stored in the database for 6 days, and the information about those test runs that have been stored for greater than 6 days is deleted at 4:00 AM.

### Example 6: Set email parameters
```
PS C:\>Set-HpcClusterProperty -EmailNotificationEnabled $True -EmailSmtpServer "MySmtpServer" -EmailFromAddress "pfuller@contoso.com"
```

This command sets the cluster-wide parameters *EmailNotificationEnabled*, *EmailSmtpServer*, and *EmailFromAddress* to $True, MySmtpServer, and pfuller@contoso.com, respectively.
As a result, email notification about jobs is turned on and the HPC job scheduler service sends those emails by using the SMTP server named MySmtpServer and from an address of someone@contoso.com.

### Example 7: Set the scheduling mode
```
PS C:\>Set-HpcClusterProperty -SchedulingMode Balanced -PriorityBias MediumBias
```

This command sets the scheduling mode to Balanced, the priority bias to MediumBias, and the rebalancing interval to 15 seconds.

## PARAMETERS

### -ActivationFilterProgram
Specifies the path and file name of the activation filter program, if one exists.
The activation filter program is called every time a job starts.
You can use the activation filter program to delay the start of a job.

You cannot specify both the *ActivationFilterProgram* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: String
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ActivationFilterTimeout
Specifies the number of seconds that the activation filter program can run before the job scheduler cancels the activation filter program and starts the job.
The range of valid values is from 1 to 120.

You cannot specify both the *ActivationFilterTimeout* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Int32
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AffinityType
Specifies a processor affinity setting that controls the association between tasks and cores.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 1 (SP1).
It is not supported in previous versions.

```yaml
Type: AffinityMode
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllocationHistoryTtl
Specifies the number of days that the HPCReporting database should store information about the allocation of jobs to nodes.

If you specify the *AllocationHistoryTtl* parameter, the only additional parameters that you can specify are the *Scheduler* parameter and the common parameters.

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: Int32
Parameter Sets: allocationHistoryTtl
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowNewUserConnections
Indicates whether the HPC job scheduler service should allow users to connect to the HPC job scheduler service to create and submit new jobs and tasks.

A nonzero value or $True indicates that the HPC job scheduler service should allow users to connect to the HPC job scheduler service to create and submit new jobs and tasks.
The HPC job scheduler service places the jobs in a queue and runs them in the order defined by the scheduling policy for the HPC cluster.

A value of 0 or $False indicates that the HPC job scheduler service should allow only cluster administrators and system services that are running on the head node of the HPC cluster to connect to the HPC job scheduler service, and it should not allow users without administrator privileges to connect to the HPC job scheduler service.
Use a setting of $False when you are doing maintenance work for the cluster and you need to prevent users from accessing the HPC job scheduler service and its database.
For example, you would use a setting of $False while you are backing up and restoring the database.
This setting does not prevent cluster administrators from creating and submitting jobs and tasks.

When you upgrade an HPC cluster, the AllowNewUserConnections property for the cluster is initially set to $False, and it automatically resets to $True when the upgrade is complete.

You cannot specify both the *AllowNewUserConnections* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: Boolean
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutomaticGrowthEnabled
Indicates whether to automatically add free resources to running jobs that still have additional tasks to run.

A non-zero value or $True indicates that the job scheduler should automatically add free resources to running jobs that still have additional tasks to run.

A value of 0 or $False indicates that the job scheduler should not automatically add free resources to running jobs that still have additional tasks to run.

You cannot specify both the *AutomaticGrowthEnabled* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Boolean
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutomaticShrinkEnabled
Indicates whether to automatically remove unneeded resources from running jobs that have no additional tasks to run.

A non-zero value or $True indicates that the job scheduler should automatically remove unneeded resources from running jobs that have no additional tasks to run.

A value of 0 or $False indicates that the job scheduler should not automatically remove unneeded resources from running jobs that have no additional tasks to run.

You cannot specify both the *AutomaticShrinkEnabled* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Boolean
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureCollectionInterval
Specifies the amount of time in seconds that should elapse between successive attempts to get values for the counters from Azure nodes.
The possible values you can specify are from 0 through 30.
If you specify 0, attempts to get values for the counters from Azure nodes occur at 60 second intervals.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 1 (SP1).
It is not supported in previous versions.

```yaml
Type: Int32
Parameter Sets: azureCollectionInterval
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureIaaSMetricsCollectionEnabled
Indicates whether to collect cluster usage data on a head node deployed in Azure infrastructure services (IaaS).
This parameter is ignored if the head node is not deployed in Azure.

This parameter was introduced in HPC Pack 2012 R2 Update 1.
It is not supported in previous versions.

```yaml
Type: Boolean
Parameter Sets: azureIaaSMetricsCollectionEnabled
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureLogsToBlob
Specifies whether to turn on or off the transfer of trace log files from Azure worker nodes or proxy nodes to a container in blob storage (hpclogs) in the Azure storage account for each node deployment.
Valid values for this parameter are:

- Disabled.
No log files are transferred to blob storage (default)
- Proxy.
Only log files from the proxy nodes in with the deployment are transferred to blob storage
- Compute.
Only log files from the worker nodes in the deployment are transferred to blob storage
- All.
Log files from the proxy nodes and the worker nodes in the deployment are transferred to blob storage

Changing this parameter only affects transfer of trace logs for future Azure node deployments.
The current deployments are not affected.

Important: Saving Azure deployment log files in blob storage uses storage space and generates storage transactions on the storage account associated with each deployment.
If enabled, saving log files from worker nodes can affect the performance of all Azure deployments that use the same storage account, especially if you have large deployments, or several concurrent deployments.
The storage space and the storage transactions will be billed to your account.
After you disable transfer of log files, the log files will not be automatically removed from Azure storage.
You may want to keep the log files for future reference by downloading them.
The log files can be cleaned up by removing the hpclogs container from your storage account.

For more information about logging for Azure nodes, see Troubleshoot Deployments of Windows Azure Nodes with Microsoft HPC Packhttp://go.microsoft.com/fwlink/p/?LinkId=273926 (http://go.microsoft.com/fwlink/p/?LinkId=273926) in the TechNet library.

This parameter was introduced in HPC Pack 2012 with Service Pack 1 (SP1).
It is not supported in previous versions.

```yaml
Type: String
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureLogsToBlobInterval
Specifies the interval in minutes between successive uploads of trace log files from Azure nodes to Azure blob storage, when transfer of logs is enabled by the *AzureLogsToBlob* parameter.
Valid values for this parameter are in the range 1 - 10 minutes.

Modify this parameter only with the assistance of Microsoft Support.

This parameter was introduced in HPC Pack 2012 with Service Pack 1 (SP1).
It is not supported in previous versions.

```yaml
Type: Int32
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureLogsToBlobThrottling
Specifies a maximum percentage of the network bandwidth of an Azure node to allow for transfer of trace log files from Azure nodes to Azure blob storage, when transfer of logs is enabled by the *AzureLogsToBlob* parameter.
Valid values for this parameter are in the range 1 - 1000, corresponding to 0.1% to 100% of the available network bandwidth.

Modify this parameter only with the assistance of Microsoft Support.

This parameter was introduced in HPC Pack 2012 with Service Pack 1 (SP1).
It is not supported in previous versions.

```yaml
Type: Int32
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureMetricsCollectionEnabled
Indicates whether to collect on the cluster head node and upload to Microsoft certain metrics about the availability, connectivity, and performance of your Azure node deployments.
For more information about the collection of these metrics, see the Privacy Statement for Microsoft HPC Packhttp://go.microsoft.com/fwlink/p/?LinkId=296260 (http://go.microsoft.com/fwlink/p/?LinkId=296260).

A non-zero or $True value turns on the collection of metrics for Azure node deployments.
A value of 0 or $False turns off the collection of metrics for Azure node deployments.
Changing this parameter only affects collection of metrics for future Azure node deployments.
The current deployments are not affected.

This parameter was introduced in HPC Pack 2012 with Service Pack 1 (SP1).
It is not supported in previous versions.

```yaml
Type: Boolean
Parameter Sets: azureMetricsCollectionEnabled
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureMetricsJobStatisticsDelayMinutes
Specifies an offset in minutes for inclusion of job history information in the metrics that are collected from Azure nodes, when metrics collection is enabled by the AzureMetricsCollectionEnabled parameter.
Jobs that run on Azure nodes in the last interval specified by this parameter are not represented in aggregate statistics.

This parameter was introduced in HPC Pack 2012 with Service Pack 1 (SP1).
It is not supported in previous versions.

```yaml
Type: Int32
Parameter Sets: azureMetricsJobStatisticsDelayMinutes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureStorageConnectionString
Specifies an Azure storage connection string to enable the use of common data and service-oriented architecture (SOA) session monitoring when running SOA jobs on Azure nodes.
For configuration details, see Configuring Connection Stringshttp://msdn.microsoft.com/library/ee758697.aspx.

This parameter was introduced in HPC Pack 2012.
It is not supported in previous versions.

```yaml
Type: String
Parameter Sets: azureStorageConnectionString
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackfillLoadPeriod
Specifies the time in seconds that the job scheduler searches the job queue to find jobs that can backfill the jobs at the top of the job queue.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 3 (SP3).
It is not supported in previous versions.

```yaml
Type: Int32
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackfillLookAhead
Specifies the number of jobs that the job scheduler searches to find jobs that can backfill the jobs at the top of the job queue.

A value of 0 indicates that the job scheduler should not backfill the jobs at the top of the job queue.

A negative value indicates that the job scheduler should search though the entire job queue to find jobs that can backfill the jobs at the top of the job queue.

You cannot specify both the *BackfillLookAhead* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Int32
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CollectCounters
Indicates whether to turn the collection of performance counter data on or off.
If you turn off the collection of performance counter data, the heat maps and charts will not show any data from the moment you turn off data collection, and the Get-HpcMetricValue cmdlet will not show any performance counter values.

A non-zero or $True value turns the collection of performance counter data on.
A value of 0 or false turns the collection of performance counter data off.

If you specify the *CollectCounters* parameter, the only additional parameters that you can specify are the Scheduler parameter and the common parameters.

```yaml
Type: Boolean
Parameter Sets: collectCounters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConcurrencyTestRunNumber
Specifies the maximum number of diagnostic tests that the HPC cluster can run simultaneously.
Specify 0 to allow an unlimited number of diagnostic tests to run simultaneously.

You cannot specify both the *ConcurrencyTestRunNumber* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: String
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataExtensibilityEnabled
Indicates whether the cluster stores information for custom reporting about jobs, nodes, and the allocation of jobs to nodes.

A nonzero value or $True indicates that the cluster stores information for custom reporting about jobs, nodes, and the allocation of jobs to nodes.
A value of 0 or $False indicates that the cluster does not store this information.

If you specify the *DataExtensibilityEnabled* parameter, the only additional parameters that you can specify are the Scheduler parameter and the common parameters.

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: Boolean
Parameter Sets: dataExtensibilityEnabled
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataExtensibilityTtl
Specifies the number of days that the HPCReporting database should store all of the information about jobs and nodes except for the allocation of jobs to nodes.

If you specify the *DataExtensibilityTtl* parameter, the only additional parameters that you can specify are the *Scheduler* parameter and the common parameters.

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: Int32
Parameter Sets: dataExtensibilityTtl
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DayCounterRetention
Specifies how often data for the day performance counters gets deleted from the database, in days.
For example, if the value is 180, the data for the day performance counters is deleted every 180 days.

If you specify the *DayCounterRetention* parameter, the additional parameters that you can specify are *HourCounterRetention*, *MinuteCounterRetention*, *Scheduler*, and the common parameters.
If you specify the *DayCounterRetention* parameter, the only additional parameters that you can specify are the *Scheduler* parameter and the common parameters.

This parameter was introduced in HPC Pack 2012.
It is not supported in previous versions.

```yaml
Type: Int32
Parameter Sets: PerfCounterRetention
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultHoldDuration
Specifies the default amount of time in seconds before the HPC job scheduler service reevaluates jobs that are placed on hold by an activation filter program.

You cannot specify both the *DefaultHoldDuration* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: Int32
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableCredentialReuse
Indicates whether the HPC job scheduler service is enabled to cache the credentials that are used to submit a job.
A nonzero value or $True indicates that the job scheduler cannot cache the credentials.
A value of 0 or $False indicates that the job scheduler can cache credentials.
If caching is enabled, a prompt to cache the password appears after new credentials are supplied to submit a job.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 3 (SP3).
It is not supported in previous versions.

```yaml
Type: Boolean
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EmailCredential
Specifies the user account that the HPC cluster uses to send email notifications, if the email server requires credentials.
The account must have administrative permissions on the head node.

If you specify the *EmailCredential* parameter, the only additional parameters that you can specify are the *Scheduler* parameter and the common parameters.

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: PSCredential
Parameter Sets: emailCredential
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EmailFromAddress
Specifies the email address to use on the From line for email notifications.

You cannot specify both the *EmailFromAddress* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: String
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EmailNotificationEnabled
Indicates whether the HPC job scheduler service should send email notifications about jobs when job owners specify that they want to receive such notifications.

A nonzero value or $True indicates that the HPC job scheduler service should send email notifications about jobs.
A value of 0 or $False indicates that the HPC job scheduler service should not send email notifications about jobs.

You cannot specify both the *EmailNotificationEnabled* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: Boolean
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EmailSmtpServer
Specifies the name or IP address of the Simple Mail Transfer Protocol (SMTP) server that the HPC job scheduler service should use to send email notifications, if email notifications are enabled.

You cannot specify both the *EmailSmtpServer* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: String
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EmailUseSsl
Indicates whether the SMTP server that the HPC job scheduler service uses to send email notifications requires a secure connection.
A nonzero value or $True indicates that the SMTP server requires a secure connection.
A value of 0 or $False indicates that the SMTP server does not require a secure connection.

You cannot specify both the *EmailUseSsl* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: Boolean
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnablePools
Indicates whether resource pools are enabled on the HPC job scheduler service.
A nonzero value or $True indicates that resource pools are enabled.
A value of 0 or $False disables resource pools.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 2 (SP2).
It is not supported in previous versions.

```yaml
Type: Boolean
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Environment
Sets cluster-wide environment variables in the environments on all of the compute nodes so that applications that run on the HPC cluster can use the environment variables.
Specify the environment variables that you want to set and their values in the following format:

"name1=value1"\[,"name2=value2"\[,"name3=value3"...\]

To delete an environment variable, omit the value for the variable.
For example, `"name1=","name2=20"` deletes the environment variable named name1 and sets the environment variable named name2 to 20.

If you specify the *Environment* parameter, the only additional parameters that you can specify are the *Scheduler* parameter and the common parameters.

```yaml
Type: String[]
Parameter Sets: environment
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludedNodesLimit
Specifies the maximum number of nodes that you can add to the list of nodes on which a job should not run.
For SOA jobs, the broker cancels sessions that try to exclude a greater number of nodes than are specified by this setting.
For other types of jobs, an error occurs if you try to add a greater number of nodes than are specified by this setting to the list of nodes on which a job should not run.

You cannot specify both the *ExcludedNodesLimit* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: Int32
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GrowByPreemptionEnabled
Indicates whether the HPC job scheduler service is enabled to take resources from lower priority, running jobs to add resources to higher priority, running jobs.
A nonzero value or $True indicates that task-level preemption is enabled.
A value of 0 or $False indicates that task-level preemption is not enabled.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 2 (SP2).
It is not supported in previous versions.

```yaml
Type: Boolean
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HeartbeatInterval
Specifies how often the job scheduler sends health probes to the HPC Node Manager Service to confirm that the nodes in the HPC cluster are still reachable.
This interval is specified in seconds.

You cannot specify both the *HeartbeatInterval* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Int32
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HourCounterRetention
Specifies how often data for the hour performance counters gets deleted from the database, in days.
For example, if the value is 30, the data for the hour performance counters is deleted every 30 days.

If you specify the *HourCounterRetention* parameter, the additional parameters that you can specify are *MinuteCounterRetention*, *DayCounterRetention*, *Scheduler*, and the common parameters.

This parameter was introduced in HPC Pack 2012.
It is not supported in previous versions.

```yaml
Type: Int32
Parameter Sets: PerfCounterRetention
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HpcSoftCard
Specifies the HPC soft card policy on the HPC job scheduler service.
By default, the HpcSoftCard cluster property is set to Disabled.
If you want users to always use soft card authentication, set the property to Required.
If you want users to select between a password and a soft card to log on, set the property to Allowed.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 2 (SP2).
It is not supported in previous versions.

```yaml
Type: HpcSoftCardPolicy
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HpcSoftCardTemplate
Specifies the name of the certificate template that will be used to create new HPC soft cards for the cluster.
When users want to access the cluster, they can generate a soft card credential that is based on this template by running New-HpcSoftCard.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 2 (SP2).
It is not supported in previous versions.

```yaml
Type: String
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InactivityCount
Specifies the number of heartbeats a compute node can miss before the job scheduler declares the node unreachable.
A compute node misses a heartbeat if there is no reply from the health probes.

Before HPC Pack 2012 with Service Pack 1 (SP1), the *InactivityCount* parameter applies to both on-premises compute nodes and Azure nodes.
Starting with HPC Pack 2012 with SP1, the *InactivityCount* parameter applies only to on-premises compute nodes.
The *InactivityCountAzure* parameter is introduced to configure Azure nodes separately.

You cannot specify both the *InactivityCount* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Int32
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InactivityCountAzure
Specifies the number of heartbeats an Azure node can miss before the job scheduler declares the node unreachable.
An Azure node misses a heartbeat if there is no reply from the health probes.

You cannot specify both the *InactivityCount* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

This parameter was introduced in HPC Pack 2012 with Service Pack 1 (SP1).
It is not supported in previous versions.

```yaml
Type: Int32
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstallCredential
Specifies a **PSCredential** object for the credentials to use to install compute nodes and run diagnostic tests.
Use the Get-Credential cmdlet to get a **PSCredential** object.
Alternatively, you can specify a user in the domain\user_name format, and then the **Set-HpcClusterProperty** cmdlet prompts you for a password.

If you specify the *InstallCredential* parameter, the only additional parameters that you can specify are the *Scheduler* parameter and the common parameters.

```yaml
Type: PSCredential
Parameter Sets: installCredential
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobCleanUpHour
Specifies the hour of the day in 24-hour time at which the job scheduler should delete old job records from the database.
For example, a value of 23 causes the job scheduler to delete job records that are older than the number of days that the TTLCompletedJobs property specifies at 11:00 PM each day.
The value of this parameter must be between 0 and 23.

You cannot specify both the *JobCleanupHour* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Int32
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobRetryCount
Specifies the maximum number of times that the job scheduler automatically tries to rerun a job before marking the job as failed.
The value range for this parameter is from 0 to 2,147,483,647.

You cannot specify both the *JobRetryCount* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Int32
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinuteCounterRetention
Specifies how often data for the minute performance counters gets deleted from the database, in days.
For example, if the value is 3, the data for the minute performance counters is deleted every three days.

If you specify the *MinuteCounterRetention* parameter, the additional parameters that you can specify are *HourCounterRetention*, *DayCounterRetention*, *Scheduler*, and the common parameters.

```yaml
Type: Int32
Parameter Sets: PerfCounterRetention
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NettcpOver443
Indicates whether the HPC job scheduler service communicates with an Azure node deployment by using a NetTcp binding on port 443.
A nonzero value or $True indicates that a NetTcp binding on port 443 is enabled.
A value of 0 or $False indicates that the communication uses the HTTPS protocol on port 443.

This parameter was introduced in HPC Pack 2012.
It is not supported in previous versions.

```yaml
Type: Boolean
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeNamingSequenceCount
Specifies the number in the node naming series after which names are generated for newly added compute nodes.
For example, if this parameter is set to 24 and the *NodeNamingSeries* parameter is set to Node-%10%, the next compute node added will be named Node-25.

This parameter was introduced in HPC Pack 2012 R2 Update 1.
It is not supported in previous versions.

```yaml
Type: Int32
Parameter Sets: nodeNameSequence
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeNamingSeries
Specifies the naming series to use to generate names for new compute nodes.
The format of the naming series should consist of alphabetic characters and a number between percent characters (%), such as MyCluster%1000%.
The maximum length of the string for the naming series is 17 characters.

The name for the first compute node will be the string for the naming series without the percent characters; for example, MyCluster1000.
The names for subsequent compute nodes increment the numeric portion of the name by one for each new node, until the highest number with the same number of digits that the naming series that you specified is reached; for example, MyCluster1001, MyCluster1002, MyCluster1003,...MyCluster9999.

If you specify the *NodeNamingSeries* parameter, the only additional parameters that you can specify are the *Scheduler* parameter and the common parameters.

```yaml
Type: String
Parameter Sets: nodeNameSeries
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeReleaseTaskTimeout
Specifies the maximum run time in seconds for Node Release tasks.

Node Release tasks run even when a job is canceled.
A cluster administrator or the job owner can force a job that is being canceled to skip the Node Release task.

You cannot specify both the *NodeReleaseTaskTimeout* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: Int32
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperationArchive
Specifies the interval in days between processes to archive operation log data in the HPCManagement database.
For example, if the value is 7, operation log data is archived every 7 days.

This parameter was introduced in HPC Pack 2012 R2 Update 1.
It is not supported in previous versions.

```yaml
Type: Int32
Parameter Sets: operationArchive
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperationRetention
Specifies the number of days that the archived operation log data is retained in the HPCManagement database.
For example, if the value is 180, an archive is deleted after 180 days.

This parameter was introduced in HPC Pack 2012 R2 Update 1.
It is not supported in previous versions.

```yaml
Type: Int32
Parameter Sets: operationRetention
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreemptionBalancedMode
Specifies the type of preemption that the job scheduler applies when the SchedulingMode property is set to Balanced.

This parameter was introduced in HPC Pack 2012 with Service Pack 1 (SP1).
It is not supported in previous versions.
In previous versions, in Balanced mode, pre-emption is always Immediate.

```yaml
Type: String
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreemptionType
Specifies the type of preemption that the job scheduler applies when the SchedulingMode property is set to Queued.

You cannot specify both the *PreemptionType* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: PreemptionMode
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PriorityBias
Specifies how additional resources are allocated to jobs when the SchedulingMode property is set to Balanced.
In the Balanced scheduling mode, additional resources are the cluster resources that exceed the total minimum resources for all running jobs.
In the Queued scheduling mode, the PriorityBias setting has no effect.

You cannot specify both the *PriorityBias* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: PriorityBias
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReBalancingInterval
Specifies the amount time in seconds between successive operations that the HPC job scheduler service performs to rebalance the allocation of resources in the Balanced scheduling mode.
The HPC job scheduler service adds or removes resources from job during these operations to start new jobs, fill available resources, and balance resource allocation based on the setting of the PriorityBias property.

You cannot specify both the *ReBalancingInterval* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: Int32
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestoreMode
Specifies whether the HPC job scheduler service is in restore mode.
The HPC job scheduler service restore mode helps bring the cluster to a consistent state in the case that you are performing a database or system restore.

A nonzero value or $True will set the HPC job scheduler service in restore mode.
A value of 0 or $False will turn restore mode on the HPC job scheduler service off.

This parameter defaults to true, if no value is specified.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 2 (SP2).
It is not supported in previous versions.

```yaml
Type: SwitchParameter
Parameter Sets: restoreMode
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunCleanUpHour
Specifies the hour of the day in 24-hour time at which the HPC Diagnostics Service should delete old records for diagnostic test runs from the database.
For example, a value of 23 causes the HPC Diagnostics Service to delete records for test runs that are older than the number of days that the TtlCompletedRuns property specifies at 11:00 PM each day.
The value of this parameter must be between 0 and 23.

You cannot specify both the *RunCleanupHour* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: String
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
You cannot specify both the *ActivationFilterProgram* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

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

### -SchedulingMode
Specifies how to optimize resource allocation for large batch and Message Passing Interface (MPI) workloads or for service workloads.

You cannot specify both the *SchedulingMode* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: SchedulingMode
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SoftCardExpirationWarning
Specifies the number of days until the soft card certificate expiration date.
If the expiration date is equal to or less than the specified number of days, HPC soft card users will receive a warning that their certificate is about to expire.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 2 (SP2).
It is not supported in previous versions.

```yaml
Type: Int32
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubmissionFilterProgram
Specifies the file name and path for the submission filter program, if one exists.
The submission filter program runs every time a job is submitted.
You can use the submission filter program to reject or change jobs that users submit to the job scheduler.

You cannot specify both the *SubmissionFilterProgram* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: String
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubmissionFilterTimeout
Specifies the number of seconds that the submission filter program can run before the job scheduler cancels the submission filter program and rejects the job.
The range of valid values is from 1 to 120.

You cannot specify both the *SubmissionFilterTimeout* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Int32
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TaskCancelGracePeriod
Specifies the amount of time in seconds that the HPC Node Manager Service should allow applications to use to exit gracefully.

In Microsoft HPC Pack, the HPC Node Manager Service stops a running task by sending a CTRL+BREAK signal to the application.
To make use of the grace period for task cancellation, the application must include code to handle the CTRL+BREAK event.
If the application does not respond to the CTRL+BREAK event, it exits immediately.
For an SOA service to use the grace period, it must respond to the ServiceContext.OnExiting event.

You cannot specify both the *TaskCancelGracePeriod* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: Int32
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TaskImmediatePreemptionEnabled
Indicates whether the HPC job scheduler service is enabled to cancel a task in a job to allow a higher priority job in the queue to start.
Unlike the job-level preemption that is configured with the *PreemptionType* parameter, which cancels the lower priority job and requeues it, task-level preemption can allow a job to continue running even if some of its tasks are preempted on some cluster resources.
A nonzero value or $True indicates that task-level preemption is enabled.
A value of 0 or $False indicates that task-level preemption is not enabled.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 3 (SP3).
It is not supported in previous versions.

```yaml
Type: Boolean
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TaskRetryCount
Specifies the maximum number of times that the job scheduler automatically tries to rerun a task before marking the task as failed.

You cannot specify both the *TaskRetryCount* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Int32
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TtlCompletedJobs
Specifies the number of days that information about completed jobs remains in the SQL database before the job scheduler deletes the records.
A completed job is a job in the Finished, Failed, or Canceled state.

You cannot specify both the *TtlCompletedJobs* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Int32
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TtlCompletedRuns
Specifies the number of days that information about completed diagnostic test runs remains in the SQL database before the HPC Diagnostics Service deletes the records.
A completed diagnostic test run is a test run with a state other than running.

You cannot specify both the *TtlCompletedRuns* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: String
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WDSMode
Specifies the value of the setting that indicates whether Windows Deployment Services on the head node responds to all Pre-Boot Execution Environment (PXE) requests, or only to the requests that come from existing compute nodes.

If you specify the *WDSMode* parameter, the only additional parameters that you can specify are the *Scheduler* parameter and the common parameters.

```yaml
Type: WdsMode
Parameter Sets: wdsMode
Aliases:
Accepted values: AutoCapture, IgnoreUnknown

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableGrowShrink
You cannot specify both the *ActivationFilterProgram* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Boolean
Parameter Sets: autogrowshrink
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeNodeGroups
You cannot specify both the *ActivationFilterProgram* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: String[]
Parameter Sets: autogrowshrink
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtraNodesGrowRatio
You cannot specify both the *ActivationFilterProgram* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Int32
Parameter Sets: autogrowshrink
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GetAzureBatchTaskOutput
You cannot specify both the *ActivationFilterProgram* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Boolean
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GrowByMin
You cannot specify both the *ActivationFilterProgram* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Boolean
Parameter Sets: autogrowshrink
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GrowInterval
You cannot specify both the *ActivationFilterProgram* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Int32
Parameter Sets: autogrowshrink
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GrowThreshold
You cannot specify both the *ActivationFilterProgram* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Int32
Parameter Sets: autogrowshrink
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShrinkIdleTimes
You cannot specify both the *ActivationFilterProgram* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Int32
Parameter Sets: autogrowshrink
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShrinkInterval
You cannot specify both the *ActivationFilterProgram* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Int32
Parameter Sets: autogrowshrink
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SoaJobGrowThreshold
You cannot specify both the *ActivationFilterProgram* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Int32
Parameter Sets: autogrowshrink
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SoaRequestsPerCore
You cannot specify both the *ActivationFilterProgram* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Int32
Parameter Sets: autogrowshrink
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TasksPerResourceUnit
You cannot specify both the *ActivationFilterProgram* parameter and any of the following parameters:

- *AllocationHistoryTtl*
- *CollectCounters*
- *DataExtensibilityEnabled*
- *DataExtensibilityTtl*
- *EmailCredential*
- *Environment*
- *InstallCredential*
- *MinuteCounterRetention*
- *HourCounterRetention*
- *DayCounterRetention*
- *NodeNamingSeries*
- *WDSMode*

```yaml
Type: Int32
Parameter Sets: autogrowshrink
Aliases:

Required: False
Position: Named
Default value: None
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
* You must be a cluster administrator to run this cmdlet successfully.
* The *BrokerTaskProgram* and *ServiceTaskProgram* parameters that this cmdlet had for Windows HPC Server 2008 were removed in Windows HPC Server 2008 R2.

## RELATED LINKS

[Get-HpcClusterProperty](./Get-HpcClusterProperty.md)
