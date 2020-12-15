---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Get-HpcClusterProperty
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

# Get-HpcClusterProperty

## SYNOPSIS
Gets the cluster-wide properties for an HPC cluster.

## SYNTAX

### default (Default)
```
Get-HpcClusterProperty [-Scheduler <String[]>] [<CommonParameters>]
```

### environment
```
Get-HpcClusterProperty [[-Name] <String>] [-Environment] [-Scheduler <String[]>] [<CommonParameters>]
```

### parameter
```
Get-HpcClusterProperty [[-Name] <String>] [-Parameter] [-Scheduler <String[]>] [<CommonParameters>]
```

### installCredential
```
Get-HpcClusterProperty [-InstallCredential] [-Scheduler <String[]>] [<CommonParameters>]
```

### emailCredential
```
Get-HpcClusterProperty [-EmailCredential] [-Scheduler <String[]>] [<CommonParameters>]
```

### nodeNameSeries
```
Get-HpcClusterProperty [-NodeNamingSeries] [-Scheduler <String[]>] [<CommonParameters>]
```

### nodeNameSequence
```
Get-HpcClusterProperty [-NodeNamingSequenceCount] [-Scheduler <String[]>] [<CommonParameters>]
```

### wdsMode
```
Get-HpcClusterProperty [-WDSMode]  [-Scheduler <String[]>] [<CommonParameters>]
```

### restoreMode
```
Get-HpcClusterProperty [-RestoreMode]  [-Scheduler <String[]>] [<CommonParameters>]
```

### autogrowshrink
```
Get-HpcClusterProperty [-AutoGrowShrink] [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcClusterProperty** cmdlet gets the cluster-wide properties for the specified HPC cluster.
Cluster-wide properties include parameters, environment variables, installation credentials, credentials to use for sending email notifications, the naming series for new compute nodes, and the Windows Deployment Services mode.
If you do not specify any parameters, this cmdlet get the values for all of these items.

## EXAMPLES

### Example 1: Get the value of a configuration parameter
```
PS C:\>Get-HpcClusterProperty -Parameter -Name "SpoolDir"
```

This command gets the value of a configuration parameter for the HPC cluster named SpoolDir.

### Example 2: Get the value of an environment variable
```
PS C:\>Get-HpcClusterProperty -Environment -Name:CCP_CLUSTER_NAME
```

This command gets the value of an environment variable named CCP_CLUSTER_NAME.

### Example 3: Get the node naming series
```
PS C:\>Get-HpcClusterProperty -NodeNamingSeries
```

This command gets the naming series that is used to generate names for new compute nodes that you add to the HPC cluster.

### Example 4: Get the credentials to install nodes
```
PS C:\>Get-HpcClusterProperty -InstallCredential
```

This command gets the credentials that are used to install new compute nodes and run diagnostic tests.

### Example 5: Get email credentials
```
PS C:\>Get-HpcClusterProperty -EmailCredential
```

This command gets the credentials that are used when sending email notifications.

## PARAMETERS

### -EmailCredential
Gets the user account that the HPC cluster uses to send email notifications, if the email server requires credentials.
The account must have administrative permissions on the head node.

You cannot specify the *EmailCredential* parameter with any of the following parameters: *Environment*, *InstallCredential*, *NodeNamingSeries*, *Parameter*, and *WDSMode*.

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: SwitchParameter
Parameter Sets: emailCredential
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Environment
Gets the values of cluster-wide environment variables.
To get the value of a specific cluster-wide environment variable, use the *Name* parameter in addition to the *Environment* parameter.

The CCP_CLUSTER_NAME, CCP_MPI_NETMASK, CCP_SERVICEREGISTRATION_PATH, and WCF_NETWORKPREFIX environment variables are present by default.
The CCP_CLUSTER_NAME environment variable specifies the name of the cluster, which is the same as the name of the computer that serves as the head node.
The CCP_MPI_NETMASK environment variable specifies the network mask for the network interface that the Message Passing Interface (MPI) process uses.
The CCP_SERVICEREGISTRATION_PATH environment variable specifies the location where the configuration files for the service-oriented architecture (SOA) services should be placed to register the services, and is \\\\%CCP_CLUSTER_NAME%\HpcServiceRegistration by default.
The WCF_NETWORKPREFIX environment variable specifies the prefix for the network that the Windows Communication Foundation (WCF) broker and service use for internal traffic.

You can set the value of these environment variables and create your own environment variables by using the Set-HpcClusterProperty cmdlet.

You cannot specify the *Environment* parameter with any of the following parameters: *InstallCredential*, *EmailCredential*, *NodeNamingSeries*, *Parameter*, and *WDSMode*.

```yaml
Type: SwitchParameter
Parameter Sets: environment
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstallCredential
Gets the credentials that are used for installing new compute nodes and for running diagnostic tests.

You cannot specify the *InstallCredential* parameter with any of the following parameters: *EmailCredential*, *Environment*, *NodeNamingSeries*, *Parameter*, and *WDSMode*.

```yaml
Type: SwitchParameter
Parameter Sets: installCredential
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the parameter or environment variable for which you want to get the value.
You must also specify the *Environment* or the *Parameter* parameter when you specify the *Name* parameter.

You cannot specify the *Name* parameter with any of the following parameters: *InstallCredential*, *EmailCredential*, *NodeNamingSeries*, and *WDSMode*.

```yaml
Type: String
Parameter Sets: environment, parameter
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeNamingSequenceCount
Gets the number in the node naming series after which names are generated for newly added compute nodes.

This parameter was introduced in HPC Pack 2012 R2 Update 1.
It is not supported in previous versions.

```yaml
Type: SwitchParameter
Parameter Sets: nodeNameSequence
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeNamingSeries
Gets the naming series that is used to generate names for new compute nodes.
For example, a naming series of ComputeNode%01% generates a series of 99 node names from ComputeNode01 to ComputeNode99.

You cannot specify both the NodeNameSeries parameter and any of the following parameters: *Environment*, *InstallCredential*, *EmailCredential*, *Parameter*, and *WDSMode*.

```yaml
Type: SwitchParameter
Parameter Sets: nodeNameSeries
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameter
Gets the values of configuration parameters for the HPC cluster.
To get the value of a specific configuration parameter, use the *Name* parameter in addition to the *Parameter* parameter.
For information about a specific configuration parameter for an HPC cluster, see the description of the parameter for the Set-HpcClusterProperty cmdlet that has the same name as the configuration parameter.

You cannot specify the *Parameter* parameter with any of the following parameters: *Environment*, *InstallCredential*, *EmailCredential*, *NodeNamingSeries*, and *WDSMode*.

```yaml
Type: SwitchParameter
Parameter Sets: parameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster for which you want to get information.
The value must be a valid computer name or IP address.
If you do not specify the *Scheduler* parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.
To set this environment variable, run the following cmdlet:

`Set-Content Env:CCP_SCHEDULER \<head_node_name\>`

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

### -WDSMode
Gets the value of the Windows Deployment Services setting that indicates whether the head node responds to all Pre-Boot Execution Environment (PXE) requests, or only the requests that come from existing compute nodes.
The value is AutoCapture if the head node responds to all requests, and the value is IgnoreUnknown if the head node responds only to requests from existing compute nodes.

You cannot specify the WDSMode parameter with any of the following parameters: *Environment*, *InstallCredential*, *EmailCredential*, *NodeNamingSeries*, and *Parameter*.

```yaml
Type: SwitchParameter
Parameter Sets: wdsMode
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestoreMode
Determines if the HPC Job Scheduler Service is in restore mode.

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

### -AutoGrowShrink
You cannot specify the *EmailCredential* parameter with any of the following parameters: *Environment*, *InstallCredential*, *NodeNamingSeries*, *Parameter*, and *WDSMode*.

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: SwitchParameter
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

### HpcVariable

## NOTES
* If you do not specify the *Environment*, *InstallCredential*, *EmailCredential*, *NodeNamingSeries*, *Parameter*, or *WDSMode* parameter, the **Get-HpcClusterProperty** cmdlet gets all six types of cluster-wide properties.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Set-HpcClusterProperty](./Set-HpcClusterProperty.md)
