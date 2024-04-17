---
Download Help Link: https://aka.ms/winsvr-2012r2-pshelp
Help Version: 5.0.0.0
Locale: en-US
Module Guid: 00000000-0000-0000-0000-000000000000
Module Name: HPC
ms.date: 12/20/2016
title: HPC
---

# Microsoft HPC Pack 2012 R2
## Description
This reference provides cmdlet descriptions and syntax for all HPC cluster-specific cmdlets that are available in Microsoft HPC Pack 2012 R2, Microsoft HPC Pack 2012, and HPC Pack 2008 R2. The HPC cmdlets provide an alternative to most actions that you would otherwise perform with command-line commands, HPC Cluster Manager, or HPC Job Manager.

For information about using HPC PowerShell, see [Appendix 6: Using HPC PowerShell](https://go.microsoft.com/fwlink/?LinkId=151474) in the TechNet library.

For information about using Windows PowerShell, see [Windows PowerShell (TechNet)](https://go.microsoft.com/fwlink/?LinkId=128426) in TechNet.

For information about built-in Windows PowerShell cmdlets, see [Windows PowerShell Core Cmdlets](https://go.microsoft.com/fwlink/?LinkId=113277) in TechNet.


## HPC Cmdlets
### [Add-HpcBatchPool](./Add-HpcBatchPool.md)
Adds an Azure Batch pool to the HPC cluster.

### [Add-HpcDriver](./Add-HpcDriver.md)
Adds device drivers to all of the operating system images in an HPC cluster.

### [Add-HpcGroup](./Add-HpcGroup.md)
Adds nodes to node groups.

### [Add-HpcImage](./Add-HpcImage.md)
Adds an operating system image to the image store for an HPC cluster.

### [Add-HpcIScsiStorageArray](./Add-HpcIScsiStorageArray.md)
Adds the iSCSI storage array at the specified management IP address to an HPC cluster.

### [Add-HpcLinuxNode](./Add-HpcLinuxNode.md)
Adds Linux node to the HPC cluster.

### [Add-HpcMember](./Add-HpcMember.md)
Adds a domain account to the HPC cluster as a member in a cluster role.

### [Add-HpcNodeSet](./Add-HpcNodeSet.md)
Adds a set of Azure nodes to the HPC cluster.

### [Add-HpcNonDomainComputeNode](./Add-HpcNonDomainComputeNode.md)
Adds a non-domain-joined compute node to the HPC cluster.

### [Add-HpcPool](./Add-HpcPool.md)
Adds a resource pool to an HPC cluster.

### [Add-HpcTask](./Add-HpcTask.md)
Creates a task and adds it to a job.

### [Add-HpcTest](./Add-HpcTest.md)
Adds custom diagnostic tests to the set of diagnostic tests that administrators can run on the HPC cluster.

### [Add-HpcUnManagedNode](./Add-HpcUnManagedNode.md)
Adds unmanaged compute resources to the cluster as a compute node.

### [Assign-HpcNodeTemplate](./Assign-HpcNodeTemplate.md)
Assigns or reapplies a node template to a node.

### [Copy-HpcJobTemplate](./Copy-HpcJobTemplate.md)
Copies a job template.

### [Copy-HpcNodeTemplate](./Copy-HpcNodeTemplate.md)
Creates a node template by making a copy of an existing node template.

### [Export-HpcDHCPReservations](./Export-HpcDHCPReservations.md)
Saves information about the DHCP reservations.

### [Export-HpcJob](./Export-HpcJob.md)
Saves information about a job in an XML file.

### [Export-HpcJobTemplate](./Export-HpcJobTemplate.md)
Exports a job template to an XML file.

### [Export-HpcMetric](./Export-HpcMetric.md)
Exports the specified set of metrics that HPC Cluster Manager uses in the heat maps for the nodes and the monitoring charts to an XML file.

### [Export-HpcNodeTemplate](./Export-HpcNodeTemplate.md)
Creates an XML-based representation of a node template and stores it in a file.

### [Export-HpcNodeXml](./Export-HpcNodeXml.md)
Exports information about  compute nodes to an XML file.

### [Export-HpcTask](./Export-HpcTask.md)
Exports the settings for a task to an XML file.

### [Export-HpcTestResult](./Export-HpcTestResult.md)
Exports the test results for the specified diagnostic test run to the specified directory.

### [Get-HpcBatchPoolStartTask](./Get-HpcBatchPoolStartTask.md)
Gets the start task result from an Azure Batch pool if a start task is specified in an Azure Batch pool template.

### [Get-HpcClusterOverview](./Get-HpcClusterOverview.md)
Gets an overview of some metrics for the specified HPC cluster, including the number of nodes, jobs, and tasks in various states on the HPC cluster.

### [Get-HpcClusterProperty](./Get-HpcClusterProperty.md)
Gets the cluster-wide properties for an HPC cluster.

### [Get-HpcClusterRegistry](./Get-HpcClusterRegistry.md)
Gets configuration properties related to HPC Pack which are stored in the Service Fabric property store.

### [Get-HpcDriver](./Get-HpcDriver.md)
Gets device drivers.

### [Get-HpcGroup](./Get-HpcGroup.md)
Gets node groups.

### [Get-HpcImage](./Get-HpcImage.md)
Gets operating system images for an HPC cluster.

### [Get-HpcIScsiStorageArray](./Get-HpcIScsiStorageArray.md)
Gets HpcIScsiStorageArray objects.

### [Get-HpcJob](./Get-HpcJob.md)
Gets jobs.

### [Get-HpcJobCredential](./Get-HpcJobCredential.md)
Gets the credentials for submitting jobs.

### [Get-HpcJobHistory](./Get-HpcJobHistory.md)
Gets the job history data for all finished, canceled, and failed jobs.

### [Get-HpcJobTemplate](./Get-HpcJobTemplate.md)
Gets information for one or more specified job templates, or for all job templates if none are specified.

### [Get-HpcJobTemplateAcl](./Get-HpcJobTemplateAcl.md)
Gets the ACL for a job template.

### [Get-HpcLogUploaderConfig](./Get-HpcLogUploaderConfig.md)
Gets the configuration of the LogUploaderAgent.

### [Get-HpcMember](./Get-HpcMember.md)
Gets a member for the HPC cluster.

### [Get-HpcMetric](./Get-HpcMetric.md)
Gets metrics that HPC Cluster Manager uses in the heat maps for the nodes and the monitoring charts.

### [Get-HpcMetricValue](./Get-HpcMetricValue.md)
Gets the current value of metrics that HPC Cluster Manager uses in heat maps for nodes and monitoring charts.

### [Get-HpcMetricValueHistory](./Get-HpcMetricValueHistory.md)
Gets the values for a specified metric during the specified time period.

### [Get-HpcNetworkInterface](./Get-HpcNetworkInterface.md)
Gets network interfaces on the head node.

### [Get-HpcNetworkTopology](./Get-HpcNetworkTopology.md)
Gets the current network topology for the HPC cluster.

### [Get-HpcNode](./Get-HpcNode.md)
Gets nodes in the HPC cluster.

### [Get-HpcNodeStateHistory](./Get-HpcNodeStateHistory.md)
Gets the history of changes to the state of the nodes in the HPC cluster for the specified time period.

### [Get-HpcNodeTemplate](./Get-HpcNodeTemplate.md)
Gets a node template for an HPC cluster.

### [Get-HpcOperation](./Get-HpcOperation.md)
Gets an operation.

### [Get-HpcOperationLog](./Get-HpcOperationLog.md)
Gets the log and substeps for the specified operation.

### [Get-HpcPool](./Get-HpcPool.md)
Gets a resource pool.

### [Get-HpcTask](./Get-HpcTask.md)
Gets a task or subtask for a job.

### [Get-HpcTest](./Get-HpcTest.md)
Gets diagnostic tests for the HPC cluster.

### [Get-HpcTestDetail](./Get-HpcTestDetail.md)
Gets detailed information about a diagnostic test.

### [Get-HpcTestResult](./Get-HpcTestResult.md)
Gets test runs.

### [Get-HpcTestResultDetail](./Get-HpcTestResultDetail.md)
Gets detailed information about the results of a run for a diagnostic test.

### [Import-HpcJobTemplate](./Import-HpcJobTemplate.md)
Imports a job template from an XML file.

### [Import-HpcMetric](./Import-HpcMetric.md)
Imports metrics from the specified XML file to create new metrics or overwrite existing metrics that HPC Cluster Manager uses in the heat maps for the nodes and the monitoring charts.

### [Import-HpcNodeTemplate](./Import-HpcNodeTemplate.md)
Imports node template XML files.

### [Import-HpcNodeXml](./Import-HpcNodeXml.md)
Imports nodes from the lists of nodes in one or more specified node XML files, and adds the nodes to the HPC cluster.

### [Invoke-HpcTest](./Invoke-HpcTest.md)
Runs the specified diagnostic tests on one or more specified nodes.

### [New-HpcGroup](./New-HpcGroup.md)
Creates a node group.

### [New-HpcImage](./New-HpcImage.md)
Creates an operating system image and adds it to the image store for an HPC cluster.

### [New-HpcJob](./New-HpcJob.md)
Creates a job, or creates a copy of an existing job.

### [New-HpcNodeTemplate](./New-HpcNodeTemplate.md)
Creates a node template and optionally associates an operating system image with the node template.

### [New-HpcSoftCard](./New-HpcSoftCard.md)
Generates an HPC soft card certificate.

### [Remove-HpcAzureNode](./Remove-HpcAzureNode.md)
Removes one or more Azure nodes from an HPC cluster.

### [Remove-HpcDriver](./Remove-HpcDriver.md)
Removes a device driver.

### [Remove-HpcGroup](./Remove-HpcGroup.md)
Removes the association between one or more specified node groups and one or more specified nodes.

### [Remove-HpcImage](./Remove-HpcImage.md)
Removes operating system images from the image store for an HPC cluster.

### [Remove-HpcIScsiStorageArray](./Remove-HpcIScsiStorageArray.md)
Removes the specified iSCSI storage array from the HPC cluster.

### [Remove-HpcJobCredential](./Remove-HpcJobCredential.md)
Deletes cached credentials that the job scheduler uses to submit jobs.

### [Remove-HpcJobTemplate](./Remove-HpcJobTemplate.md)
Deletes a job template.

### [Remove-HpcMember](./Remove-HpcMember.md)
Removes members from the HPC cluster or from specified roles.

### [Remove-HpcMetric](./Remove-HpcMetric.md)
Removes metrics from the set of metrics that HPC Cluster Manager uses in the heat maps for the nodes and the monitoring charts.

### [Remove-HpcNode](./Remove-HpcNode.md)
Removes the entry for one or more nodes from the HPC cluster management database.

### [Remove-HpcNodeSet](./Remove-HpcNodeSet.md)
Removes a set of Azure nodes from an HPC cluster.

### [Remove-HpcNodeTemplate](./Remove-HpcNodeTemplate.md)
Deletes node templates from the HPC cluster.

### [Remove-HpcPool](./Remove-HpcPool.md)
Removes a resource pool.

### [Remove-HpcSoaCredential](./Remove-HpcSoaCredential.md)
Deletes the cached credentials for users that SOA clients use to create SOA sessions.

### [Remove-HpcTest](./Remove-HpcTest.md)
Removes the diagnostic test with the specified alias from the HPC cluster.

### [Remove-HpcTestCredential](./Remove-HpcTestCredential.md)
Clears the cached credentials that the HPC Diagnostics Service uses to run diagnostic tests.

### [Remove-HpcTestResultAlert](./Remove-HpcTestResultAlert.md)
Clears the alert icon for diagnostic test runs.

### [Remove-HpcTokenCache](./Remove-HpcTokenCache.md)
Removes the client Microsoft Entra token cache used for job submission.

### [Replicate-HpcImage](./Replicate-HpcImage.md)
Copies a base-node operating system image from a Windows image (.wim) file to an Internet SCSI (iSCSI) storage array.

### [Restart-HpcNode](./Restart-HpcNode.md)
Restarts a node that is already turned on.

### [Set-HpcClusterProperty](./Set-HpcClusterProperty.md)
Sets cluster-wide properties.

### [Set-HpcClusterRegistry](./Set-HpcClusterRegistry.md)
Sets configuration properties related to HPC Pack which are stored in the Service Fabric property store.

### [Set-HpcGroup](./Set-HpcGroup.md)
Modifies the name or description of a node group.

### [Set-HpcIScsiStorageArray](./Set-HpcIScsiStorageArray.md)
Sets an iSCSI storage array for an HPC cluster.

### [Set-HpcJob](./Set-HpcJob.md)
Sets the properties of the specified job.

### [Set-HpcJobCredential](./Set-HpcJobCredential.md)
Sets the credentials for submitting jobs.

### [Set-HpcJobTemplateAcl](./Set-HpcJobTemplateAcl.md)
Sets the ACL on a job template.

### [Set-HpcLogUploaderConfig](./Set-HpcLogUploaderConfig.md)
Sets the configuration of the LogUploaderAgent.

### [Set-HpcNetwork](./Set-HpcNetwork.md)
Sets the network topology and the properties of all of the network interfaces for the HPC cluster.

### [Set-HpcNode](./Set-HpcNode.md)
Changes the properties for a node.

### [Set-HpcNodeState](./Set-HpcNodeState.md)
Sets the state a node.

### [Set-HpcPool](./Set-HpcPool.md)
Sets the weight of a resource pool.

### [Set-HpcSoaCredential](./Set-HpcSoaCredential.md)
Sets the credentials for creating SOA sessions.

### [Set-HpcTask](./Set-HpcTask.md)
Sets the properties for a task.

### [Set-HpcTestCredential](./Set-HpcTestCredential.md)
Sets the credentials for running diagnostic tests.

### [Set-HpcTokenCache](./Set-HpcTokenCache.md)
Sets the client Microsoft Entra token cache for job submission.

### [Shutdown-HpcNode](./Shutdown-HpcNode.md)
Turns off one or more nodes.

### [Start-HpcAzureNode](./Start-HpcAzureNode.md)
Starts Azure nodes.

### [Start-HpcBatchPool](./Start-HpcBatchPool.md)
Starts an Azure Batch pool in the HPC cluster.

### [Start-HpcNode](./Start-HpcNode.md)
Turns on nodes by using an Intelligent Platform Management Interface (IPMI) script.

### [Start-HpcNodeSet](./Start-HpcNodeSet.md)
Starts a set of Azure nodes.

### [Stop-HpcAzureNode](./Stop-HpcAzureNode.md)
Stops Azure nodes.

### [Stop-HpcBatchPool](./Stop-HpcBatchPool.md)
Stop an Azure Batch pool in an HPC cluster.

### [Stop-HpcJob](./Stop-HpcJob.md)
Cancels a job.

### [Stop-HpcNodeSet](./Stop-HpcNodeSet.md)
Stops a set of Azure nodes.

### [Stop-HpcOperation](./Stop-HpcOperation.md)
Cancels the specified operation and makes the best possible attempt to revert the operation, if the operation is still running.

### [Stop-HpcTask](./Stop-HpcTask.md)
Cancels a task or subtask.

### [Stop-HpcTestResult](./Stop-HpcTestResult.md)
Cancels a diagnostic test if it is still running.

### [Submit-HpcJob](./Submit-HpcJob.md)
Submits or re-queues jobs to the HPC cluster.

### [Validate-HpcIScsiStorageArray](./Validate-HpcIScsiStorageArray.md)
Validates that the head node of the HPC cluster can communicate with an iSCSI storage array.
