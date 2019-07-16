---
Module Name: ClusterAwareUpdating
Module Guid: 4E804861-1DCE-46C1-868D-C8F2AB9D220A
Download Help Link: http://go.microsoft.com/fwlink/?linkid=285543
Help Version: 4.0.1.0
Locale: en-US
title: ClusterAwareUpdating
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
ms.assetid: a6771a5e-e72b-4188-9658-a5e07e3f5b7a
---

# ClusterAwareUpdating Module
## Description
This reference provides cmdlet descriptions and syntax for all Cluster-Aware Updating-specific cmdlets. 
It lists the cmdlets in alphabetical order based on the verb at the beginning of the cmdlet.


## ClusterAwareUpdating Cmdlets
### [Add-CauClusterRole](./Add-CauClusterRole.md)
Adds the Cluster-Aware Updating (CAU) clustered role that provides the self-updating functionality to the specified cluster.

### [Disable-CauClusterRole](./Disable-CauClusterRole.md)
Suspends the self-updating functionality on the specified cluster.

### [Enable-CauClusterRole](./Enable-CauClusterRole.md)
Re-enables the self-updating functionality on the specified cluster.

### [Export-CauReport](./Export-CauReport.md)
Exports one or more Updating Run reports into an HTML or CSV-formatted document.

### [Get-CauClusterRole](./Get-CauClusterRole.md)
Retrieves configuration properties of the Cluster-Aware Updating (CAU) clustered role on the specified cluster.

### [Get-CauPlugin](./Get-CauPlugin.md)
Retrieves information about one or more software updating plug-ins that are registered on the local computer.

### [Get-CauReport](./Get-CauReport.md)
Retrieves the Updating Run reports for all known Updating Runs, or all Updating Runs that match the specified dates or other specified parameters.

### [Get-CauRun](./Get-CauRun.md)
Retrieves status information about an Updating Run currently in progress.

### [Invoke-CauRun](./Invoke-CauRun.md)
Performs a scan of cluster nodes for applicable updates and installs those updates via an Updating Run on the specified cluster.

### [Invoke-CauScan](./Invoke-CauScan.md)
Performs a scan of cluster nodes for applicable updates and returns a list of the initial set of updates that would be applied to each node in a specified cluster.

### [Register-CauPlugin](./Register-CauPlugin.md)
Registers a Cluster-Aware Updating (CAU) software updating plug-in on the local computer.

### [Remove-CauClusterRole](./Remove-CauClusterRole.md)
Removes the Cluster-Aware Updating (CAU) clustered role from the specified failover cluster.

### [Save-CauDebugTrace](./Save-CauDebugTrace.md)
Saves Cluster-Aware Updating (CAU) debug tracing information to a local zip file.

### [Set-CauClusterRole](./Set-CauClusterRole.md)
Sets configuration properties for the Cluster-Aware Updating (CAU) clustered role on the specified cluster.

### [Stop-CauRun](./Stop-CauRun.md)
Stops an Updating Run that is in progress on a cluster.

### [Test-CauSetup](./Test-CauSetup.md)
Tests whether a cluster is properly set up to apply software updates using Cluster-Aware Updating (CAU).

### [Unregister-CauPlugin](./Unregister-CauPlugin.md)
Removes a software updating plug-in from the list of plug-ins that are used by Cluster-Aware Updating (CAU).

