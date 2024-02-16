---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
Download Help Link: https://aka.ms/winsvr-2025-pshelp
Help Version: 5.0.0.1
Locale: en-US
Module Guid: 4e804861-1dce-46c1-868d-c8f2ab9d220a
Module Name: ClusterAwareUpdating
ms.date: 09/27/2022
title: ClusterAwareUpdating
---

# ClusterAwareUpdating Module
## Description
This reference provides cmdlet descriptions and syntax for all Cluster-Aware Updating-specific
cmdlets. It lists the cmdlets in alphabetical order based on the verb at the beginning of the
cmdlet.

## ClusterAwareUpdating Cmdlets
### [Add-CauClusterRole](./Add-CauClusterRole.md)
Adds the CAU clustered role that provides the self-updating functionality to the specified cluster.

### [Disable-CauClusterRole](./Disable-CauClusterRole.md)
Suspends the self-updating functionality on the specified cluster.

### [Enable-CauClusterRole](./Enable-CauClusterRole.md)
Re-enables the self-updating functionality on the specified cluster.

### [Export-CauReport](./Export-CauReport.md)
Exports one or more Updating Run reports into an HTML or CSV-formatted document.

### [Get-CauClusterRole](./Get-CauClusterRole.md)
Gets configuration properties of the CAU clustered role on the specified cluster.

### [Get-CauPlugin](./Get-CauPlugin.md)
Gets information about one or more software updating plug-ins that are registered on the local
computer.

### [Get-CauReport](./Get-CauReport.md)
Gets the Updating Run reports for all known Updating Runs, or all Updating Runs that match the
specified dates or other specified parameters.

### [Get-CauRun](./Get-CauRun.md)
Gets status information about an updating run currently in progress.

### [Invoke-CauRun](./Invoke-CauRun.md)
Performs a scan of cluster nodes for applicable updates and installs those updates through an
updating run on the specified cluster.

### [Invoke-CauScan](./Invoke-CauScan.md)
Performs a scan of cluster nodes for applicable updates and gets a list of the initial set of
updates that are applied to each node in a specified cluster.

### [Register-CauPlugin](./Register-CauPlugin.md)
Registers a CAU software updating plug-in on the local computer.

### [Remove-CauClusterRole](./Remove-CauClusterRole.md)
Removes the CAU clustered role from the specified failover cluster.

### [Save-CauDebugTrace](./Save-CauDebugTrace.md)
Saves CAU debug tracing information to a local zip file.

### [Set-CauClusterRole](./Set-CauClusterRole.md)
Sets configuration properties for the CAU clustered role on the specified cluster.

### [Stop-CauRun](./Stop-CauRun.md)
Stops an updating run that is in progress on a cluster.

### [Test-CauSetup](./Test-CauSetup.md)
Tests whether a cluster is properly set up to apply software updates using CAU.

### [Unregister-CauPlugin](./Unregister-CauPlugin.md)
Removes a software updating plug-in from the list of plug-ins that are used by CAU.


