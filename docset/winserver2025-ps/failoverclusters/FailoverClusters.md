---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
Download Help Link: https://aka.ms/winsvr-2025-pshelp
Help Version: 5.0.3.3
Locale: en-US
Module Guid: cc3e946b-9141-48c2-95d8-d9e56594416a
Module Name: FailoverClusters
ms.date: 10/21/2022
title: FailoverClusters
---

# FailoverClusters Module
## Description
This reference provides cmdlet descriptions and syntax for all failover cluster-specific cmdlets. It
lists the cmdlets in alphabetical order based on the verb at the beginning of the cmdlet. If these
cmdlets aren't available in your PowerShell session, you may need to add the
`Failover Cluster Module for Windows PowerShell` Feature, using the following PowerShell cmd:
`Add-WindowsFeature RSAT-Clustering-PowerShell`.

## FailoverClusters Cmdlets
### [Add-ClusterCheckpoint](./Add-ClusterCheckpoint.md)
Adds a cryptographic key checkpoint or registry checkpoint for a resource.

### [Add-ClusterDisk](./Add-ClusterDisk.md)
Makes a new disk available for use in a failover cluster.

### [Add-ClusterFileServerRole](./Add-ClusterFileServerRole.md)
Creates a clustered file server resource group.

### [Add-ClusterGenericApplicationRole](./Add-ClusterGenericApplicationRole.md)
Configures high availability for an application that wasn't originally designed to run in a
failover cluster.

### [Add-ClusterGenericScriptRole](./Add-ClusterGenericScriptRole.md)
Configures an application controlled by a script that runs in Windows Script Host, within a failover
cluster.

### [Add-ClusterGenericServiceRole](./Add-ClusterGenericServiceRole.md)
Configures high availability for a service that wasn't originally designed to run in a failover
cluster.

### [Add-ClusterGroup](./Add-ClusterGroup.md)
Adds an empty resource group to the failover cluster configuration, in preparation for adding
clustered resources to the group.

### [Add-ClusterGroupSetDependency](./Add-ClusterGroupSetDependency.md)
Adds a dependency to a cluster set.

### [Add-ClusterGroupToAffinityRule](./Add-ClusterGroupToAffinityRule.md)
This command is used to add either a VM role or a group name to a cluster affinity rule.

### [Add-ClusterGroupToSet](./Add-ClusterGroupToSet.md)
Adds a group to a set.

### [Add-ClusteriSCSITargetServerRole](./Add-ClusteriSCSITargetServerRole.md)
Creates a highly available iSCSI Target server.

### [Add-ClusterNode](./Add-ClusterNode.md)
Adds a node (server) to a failover cluster.

### [Add-ClusterResource](./Add-ClusterResource.md)
Adds a resource to a clustered role, or resource group, in a failover cluster.

### [Add-ClusterResourceDependency](./Add-ClusterResourceDependency.md)
Adds a resource to the list of resources on which a particular resource depends, using AND as the
connector, within a failover cluster.

### [Add-ClusterResourceType](./Add-ClusterResourceType.md)
Adds a resource type to a failover cluster, and specifies information such as the dynamic-link
library (DLL) to use with that resource type.

### [Add-ClusterScaleOutFileServerRole](./Add-ClusterScaleOutFileServerRole.md)
Creates a clustered file server for scale-out application data.

### [Add-ClusterSharedVolume](./Add-ClusterSharedVolume.md)
Makes a volume available in Cluster Shared Volumes in a failover cluster.

### [Add-ClusterSharedVolumeToAffinityRule](./Add-ClusterSharedVolumeToAffinityRule.md)
Adds a Cluster Shared Volume (CSV) to an existing Affinity Rule.

### [Add-ClusterVirtualMachineRole](./Add-ClusterVirtualMachineRole.md)
Creates a clustered virtual machine, that is, a virtual machine that can be failed over if necessary
to a different server in the failover cluster.

### [Add-ClusterVMMonitoredItem](./Add-ClusterVMMonitoredItem.md)
Configures monitoring for a service or an Event Tracing for Windows (ETW) event so that it is
monitored on a virtual machine.

### [Block-ClusterAccess](./Block-ClusterAccess.md)
Prevents the specified user or users from accessing a failover cluster.

### [Clear-ClusterDiskReservation](./Clear-ClusterDiskReservation.md)
Clears the persistent reservation on a disk in a failover cluster.

### [Clear-ClusterNode](./Clear-ClusterNode.md)
Clears the cluster configuration from a node that was evicted from a failover cluster.

### [Disable-ClusterStorageSpacesDirect](./Disable-ClusterStorageSpacesDirect.md)
Disables S2D.

### [Enable-ClusterStorageSpacesDirect](./Enable-ClusterStorageSpacesDirect.md)
Enables S2D.

### [Get-Cluster](./Get-Cluster.md)
Gets information about one or more failover clusters in a given domain.

### [Get-ClusterAccess](./Get-ClusterAccess.md)
Gets information about permissions that control access to a failover cluster.

### [Get-ClusterAffinityRule](./Get-ClusterAffinityRule.md)
This cmdlet is used to display the given rule and what type it is.

### [Get-ClusterAvailableDisk](./Get-ClusterAvailableDisk.md)
Gets information about the disks that can support Failover Clustering and are visible to all nodes,
but aren't yet part of the set of clustered disks.

### [Get-ClusterCheckpoint](./Get-ClusterCheckpoint.md)
Retrieves a cryptographic key checkpoint or registry checkpoint for a resource.

### [Get-ClusterDiagnosticInfo](./Get-ClusterDiagnosticInfo.md)
Gets diagnostics for a cluster a cluster that contains VMs and produces a zip file containing the
data.

### [Get-ClusterFaultDomain](./Get-ClusterFaultDomain.md)
Gets the cluster fault domains in a cluster.

### [Get-ClusterFaultDomainXML](./Get-ClusterFaultDomainXML.md)
Gets the fault domain as an XML string.

### [Get-ClusterGroup](./Get-ClusterGroup.md)
Gets information about one or more clustered roles (resource groups) in a failover cluster.

### [Get-ClusterGroupSet](./Get-ClusterGroupSet.md)
Gets the group sets in the cluster.

### [Get-ClusterGroupSetDependency](./Get-ClusterGroupSetDependency.md)
Gets the cluster group sets based on dependency relationships.

### [Get-ClusterLog](./Get-ClusterLog.md)
Creates a log file for all nodes, or a specific a node, in a failover cluster.

### [Get-ClusterNetwork](./Get-ClusterNetwork.md)
Gets information about one or more networks in a failover cluster.

### [Get-ClusterNetworkInterface](./Get-ClusterNetworkInterface.md)
Gets information about one or more network adapters in a failover cluster.

### [Get-ClusterNode](./Get-ClusterNode.md)
Gets information about one or more nodes, or servers, in a failover cluster.

### [Get-ClusterOwnerNode](./Get-ClusterOwnerNode.md)
Gets information about which nodes can own a resource in a failover cluster or information about the
order of preference among owner nodes for a clustered role.

### [Get-ClusterParameter](./Get-ClusterParameter.md)
Gets detailed information about an object in a failover cluster, such as a cluster resource.

### [Get-ClusterQuorum](./Get-ClusterQuorum.md)
Gets information about the quorum configuration of a failover cluster.

### [Get-ClusterResource](./Get-ClusterResource.md)
Gets information about one or more resources in a failover cluster.

### [Get-ClusterResourceDependency](./Get-ClusterResourceDependency.md)
Gets information about the dependencies that have been configured between clustered resources in a
failover cluster.

### [Get-ClusterResourceDependencyReport](./Get-ClusterResourceDependencyReport.md)
Generates a report that lists the dependencies between resources in a failover cluster.

### [Get-ClusterResourceType](./Get-ClusterResourceType.md)
Gets information about one or more resource types in a failover cluster.

### [Get-ClusterSharedVolume](./Get-ClusterSharedVolume.md)
Gets information about Cluster Shared Volumes in a failover cluster.

### [Get-ClusterSharedVolumeState](./Get-ClusterSharedVolumeState.md)
Gets the state of Cluster Shared Volumes in a cluster.

### [Get-ClusterStorageSpacesDirect](./Get-ClusterStorageSpacesDirect.md)
Gets the S2D settings from a cluster.

### [Get-ClusterVMMonitoredItem](./Get-ClusterVMMonitoredItem.md)
Gets the list of services and events currently being monitored in the virtual machine.

### [Grant-ClusterAccess](./Grant-ClusterAccess.md)
Grants access to a failover cluster, either full access or read-only access.

### [Move-ClusterGroup](./Move-ClusterGroup.md)
Moves a clustered role (a resource group) from one node to another in a failover cluster.

### [Move-ClusterResource](./Move-ClusterResource.md)
Moves a clustered resource from one clustered role to another within a failover cluster.

### [Move-ClusterSharedVolume](./Move-ClusterSharedVolume.md)
Moves a Cluster Shared Volume (CSV) to ownership by a different node in a failover cluster.

### [Move-ClusterVirtualMachineRole](./Move-ClusterVirtualMachineRole.md)
Moves the ownership of a clustered virtual machine to a different node.

### [New-Cluster](./New-Cluster.md)
Creates a new failover cluster.

### [New-ClusterAffinityRule](./New-ClusterAffinityRule.md)
Creates new affinity rules.

### [New-ClusterFaultDomain](./New-ClusterFaultDomain.md)
Creates a fault domain in the cluster.

### [New-ClusterGroupSet](./New-ClusterGroupSet.md)
Create a names set of groups in the cluster.

### [New-ClusterNameAccount](./New-ClusterNameAccount.md)
Creates a cluster name account in Active Directory Domain Services.

### [Remove-Cluster](./Remove-Cluster.md)
Destroys an existing failover cluster.

### [Remove-ClusterAccess](./Remove-ClusterAccess.md)
Removes a user from the access list on the cluster.

### [Remove-ClusterAffinityRule](./Remove-ClusterAffinityRule.md)
Removes new affinity rules.

### [Remove-ClusterCheckpoint](./Remove-ClusterCheckpoint.md)
Removes a cryptographic key checkpoint or registry checkpoint for a resource.

### [Remove-ClusterFaultDomain](./Remove-ClusterFaultDomain.md)
Removes a fault domain.

### [Remove-ClusterGroup](./Remove-ClusterGroup.md)
Removes a clustered role, also called a resource group, from a failover cluster.

### [Remove-ClusterGroupFromAffinityRule](./Remove-ClusterGroupFromAffinityRule.md)
Removes a cluster group from an affinity rule.

### [Remove-ClusterGroupFromSet](./Remove-ClusterGroupFromSet.md)
Removes a group from a set.

### [Remove-ClusterGroupSet](./Remove-ClusterGroupSet.md)
Removes a group set from the cluster.

### [Remove-ClusterGroupSetDependency](./Remove-ClusterGroupSetDependency.md)
Removes a dependency from a group set.

### [Remove-ClusterNode](./Remove-ClusterNode.md)
Removes a node from a failover cluster.

### [Remove-ClusterResource](./Remove-ClusterResource.md)
Removes a clustered resource from the failover cluster.

### [Remove-ClusterResourceDependency](./Remove-ClusterResourceDependency.md)
Removes a dependency between two resources in a clustered role within a failover cluster.

### [Remove-ClusterResourceType](./Remove-ClusterResourceType.md)
Removes a resource type from a failover cluster.

### [Remove-ClusterSharedVolume](./Remove-ClusterSharedVolume.md)
Removes a volume from the Cluster Shared Volumes in a failover cluster, and places it in Available
Storage in the cluster.

### [Remove-ClusterSharedVolumeFromAffinityRule](./Remove-ClusterSharedVolumeFromAffinityRule.md)
Remove a cluster shared volume from an affinity rule.

### [Remove-ClusterVMMonitoredItem](./Remove-ClusterVMMonitoredItem.md)
Removes monitoring of a service or event that is currently being monitored on a virtual machine.

### [Repair-ClusterStorageSpacesDirect](./Repair-ClusterStorageSpacesDirect.md)
Repairs S2D disks.

### [Reset-ClusterVMMonitoredState](./Reset-ClusterVMMonitoredState.md)
Resets the Application Critical state of a virtual machine, so that the virtual machine is no longer
marked as being in a critical state in the cluster.

### [Resume-ClusterNode](./Resume-ClusterNode.md)
Resumes a node from the paused state or brings back drained workloads to the node or both.

### [Resume-ClusterResource](./Resume-ClusterResource.md)
Turns off maintenance for a disk resource or Cluster Shared Volume within a failover cluster.

### [Set-ClusterAffinityRule](./Set-ClusterAffinityRule.md)
Enabled or Disable an affinity rule, and update the rule type.

### [Set-ClusterFaultDomain](./Set-ClusterFaultDomain.md)
Update an existing cluster fault domain.

### [Set-ClusterFaultDomainXML](./Set-ClusterFaultDomainXML.md)
Sets the cluster fault domain using XML.

### [Set-ClusterGroupSet](./Set-ClusterGroupSet.md)
Updates a cluster group set.

### [Set-ClusterLog](./Set-ClusterLog.md)
Sets the size and level of detail for the cluster log.

### [Set-ClusterOwnerNode](./Set-ClusterOwnerNode.md)
Specifies which nodes can own a resource in a failover cluster or specifies the order of preference
among owner nodes for a clustered role, or resource group.

### [Set-ClusterParameter](./Set-ClusterParameter.md)
Controls specific properties of an object in a failover cluster, such as a resource, a group, or a
network.

### [Set-ClusterQuorum](./Set-ClusterQuorum.md)
Configures quorum options for a failover cluster.

### [Set-ClusterResourceDependency](./Set-ClusterResourceDependency.md)
Specifies the resources that a particular resource depends on within a failover cluster.

### [Set-ClusterStorageSpacesDirect](./Set-ClusterStorageSpacesDirect.md)
Sets S2D cache parameters.

### [Set-ClusterStorageSpacesDirectDisk](./Set-ClusterStorageSpacesDirectDisk.md)
Configures the system to enable S2D to claim or not claim specific physical disks.

### [Start-Cluster](./Start-Cluster.md)
Starts the Cluster service on all nodes of the cluster on which it isn't yet started.

### [Start-ClusterGroup](./Start-ClusterGroup.md)
Starts one or more clustered roles, also known as resource groups, on a failover cluster.

### [Start-ClusterNode](./Start-ClusterNode.md)
Starts the Cluster service on a node in a failover cluster.

### [Start-ClusterResource](./Start-ClusterResource.md)
Brings a resource online in a failover cluster.

### [Stop-Cluster](./Stop-Cluster.md)
Stops the Cluster service on all nodes in a failover cluster, which will stop all services and
applications configured in the cluster.

### [Stop-ClusterGroup](./Stop-ClusterGroup.md)
Stops one or more clustered roles on a failover cluster.

### [Stop-ClusterNode](./Stop-ClusterNode.md)
Stops the Cluster service on a node in a failover cluster.

### [Stop-ClusterResource](./Stop-ClusterResource.md)
Takes a resource offline in a failover cluster.

### [Suspend-ClusterNode](./Suspend-ClusterNode.md)
Suspends activity on a failover cluster node, that is, pauses the node.

### [Suspend-ClusterResource](./Suspend-ClusterResource.md)
Turns on maintenance for a disk resource or CSV so that you can run a disk maintenance tool without
triggering failover.

### [Test-Cluster](./Test-Cluster.md)
Runs validation tests for failover cluster hardware and settings.

### [Test-ClusterResourceFailure](./Test-ClusterResourceFailure.md)
Simulates a failure of a cluster resource.

### [Update-ClusterFunctionalLevel](./Update-ClusterFunctionalLevel.md)
Updates the functional level of a mixed-version cluster.

### [Update-ClusterIPResource](./Update-ClusterIPResource.md)
Renews or releases the DHCP lease for an IP address resource in a failover cluster.

### [Update-ClusterNetworkNameResource](./Update-ClusterNetworkNameResource.md)
Registers existing Network Name resources with a DNS server in a way that does not interrupt cluster
availability.

### [Update-ClusterVirtualMachineConfiguration](./Update-ClusterVirtualMachineConfiguration.md)
Refreshes the configuration of a clustered virtual machine within a failover cluster.
