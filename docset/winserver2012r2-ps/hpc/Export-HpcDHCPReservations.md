---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Export-HpcDHCPReservations
description:
keywords: powershell, cmdlet
ms.date: 12/20/2016
ms.prod: powershell
ms.topic: reference
online version: http://go.microsoft.com/fwlink/?LinkId=182659
schema: 2.0.0
ms.assetid: B0D29FB7-E5E3-466A-8247-05A7151F1734
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Export-HpcDHCPReservations

## SYNOPSIS
Saves information about the DHCP reservations.

## SYNTAX

### AllNode (Default)
```
Export-HpcDHCPReservations -Path <String> [-Force] [-Scheduler <String[]>] [<CommonParameters>]
```

### Name
```
Export-HpcDHCPReservations -Path <String> [-Force] [-Name] <String[]> [-Scheduler <String[]>] [<CommonParameters>]
```

### Node
```
Export-HpcDHCPReservations -Path <String> [-Force] -Node <HpcNode[]> [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Export-HpcDHCPReservations** cmdlet saves information about the Dynamic Host Configuration Protocol (DHCP) reservations for the specified node to the specified XML file, or for all of the nodes in the cluster if none are specified.
You can specify the nodes by name or by **HpcNode** objects that represent the nodes.

DHCP reservations of IP addresses are based on media access control (MAC) addresses.
Each reserved IP address is linked to the MAC address of the network adapter to which that IP address is assigned.

## EXAMPLES

### Example 1: Export DHCP reservations for all nodes
```
PS C:\>Export-HpcDHCPReservations -Path "C:\Reservations\AllNodes.xml"
```

This command saves information about the DHCP reservations for all of the compute nodes in the cluster to the file at C:\Reservations\AllNodes.xml.

### Example 2: Export DHCP reservations for named nodes
```
PS C:\>Export-HpcDHCPReservations -Node ComputeNode1,ComputeNode2 -Path "C:\Reservations\ComputeNodes01and02.xml"
```

This command saves information about the DHCP reservations for the compute nodes named ComputeNode01 and ComputeNode02 to the file at C:\Reservations\ComputeNodes01and02.xml.

### Example 3: Get a node and export DHCP reservations for it
```
PS C:\>Get-HpcNode -Name "ComputeNode04" | Export-HpcDHCPReservations -Path "C:\Reservations\ComputeNode04.xml" -Force
```

This command gets the **HpcNode** object for the compute node named ComputeNode04, and then specifies that object in the **Export-HpcDHCPReservations** cmdlet to save information about the DHCP reservations for that node to the file at C:\Reservations\ComputeNode04.xml.
This example overwrites the file without prompting the user if the file already exists.

## PARAMETERS

### -Force
Replaces the specified XML file if it already exists, without prompting the user.

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

### -Name
Specifies an array of the names of the nodes for which you want to export DHCP reservations.
You cannot specify both the *Name* and *Node* parameters.
To get the nodes for the HPC cluster, use the Get-HpcNode cmdlet.

```yaml
Type: String[]
Parameter Sets: Name
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Node
Specifies an array of the nodes for which you want to export DHCP reservations.
You cannot specify both the *Node* and *Name* parameters.
To get an **HpcNode** object for a node, use the Get-HpcNode command.

```yaml
Type: HpcNode[]
Parameter Sets: Node
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path
Specifies a name for the XML file in which you want to save the information about the DHCP reservations for the nodes, including the full or relative path to the file, if the **Export-HpcDHCPReservations** cmdlet should not save the file in the current directory.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node of the HPC cluster for which you want to export DHCP reservations.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcNode

## OUTPUTS

### None

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet was introduced in HPC Pack 2008 R2. It is not supported in previous versions.

## RELATED LINKS

[Export-HpcNodeXml](./Export-HpcNodeXml.md)
