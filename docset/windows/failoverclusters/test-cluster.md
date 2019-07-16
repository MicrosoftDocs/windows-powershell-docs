---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Test-Cluster
ms.reviewer:
ms.assetid: 69D30A79-E961-41C7-901A-DC04A17EAA6C
---

# Test-Cluster

## SYNOPSIS
Runs validation tests for failover cluster hardware and settings.

## SYNTAX

```
Test-Cluster [[-Node] <StringCollection>] [-Disk <Object[]>] [-Pool <Object[]>] [-ReportName <String>] [-List]
 [-Include <StringCollection>] [-Ignore <StringCollection>] [-Force] [-InputObject <PSObject>]
 [-Cluster <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Test-Cluster** cmdlet runs validation tests for failover cluster hardware and settings.
Tests can be run both before and after a cluster is set up.

Test results are captured in a file with the file name that you specify.
By running the validation tests, you can confirm that your hardware and settings are compatible with Failover Clustering.
There are multiple types of tests, including Cluster, Inventory, Network, Storage, System, and other types of tests.
Storage tests will not test online disks or storage pools that are in use by a clustered role.
To test such disks, first run **Stop-ClusterGroup** to stop the clustered role, and then run **Test-Cluster**.
After the tests are done, start the clustered roles, also known as resource groups, again.

## EXAMPLES

### Example 1: Validate local cluster
```
PS C:\> Test-Cluster
Mode                LastWriteTime     Length Name 
----                -------------     ------ ---- 
-a---        10/10/2008   6:31 PM    1132255 Test-Cluster on 2008.10.10 At 18.22.53.mht
```

This example runs all applicable cluster validation tests on the local cluster.

### Example 2: Validate specified nodes
```
PS C:\> Test-Cluster -Node "node1", "node2"
Mode                LastWriteTime     Length Name 
----                -------------     ------ ---- 
-a---        10/10/2008   6:18 PM     998032 Test-Cluster on 2008.10.10 At 18.08.24.mht
```

This example runs all cluster validation tests on the nodes named node1 and node2.
If either node1 or node2 is already a member of a cluster, then the tests will include all nodes in that cluster.

### Example 3: View tests and categories in cluster validation
```
PS C:\> Test-Cluster -List
Category                                DisplayName                             Description 
--------                                -----------                             ----------- 
Cluster Configuration                   List Cluster Core Groups                List information about the available... 
Cluster Configuration                   List Cluster Network Information        List cluster-specific network settin... 
Cluster Configuration                   List Cluster Resources                  List the resources that are configur... 
Cluster Configuration                   List Cluster Volumes                    List information for the volumes in ... 
Cluster Configuration                   List Clustered Roles                    List information about clustered roles. 
Cluster Configuration                   Validate Quorum Configuration           Validate that the current quorum con... 
Cluster Configuration                   Validate Resource Status                Validate that cluster resources are ... 
Cluster Configuration                   Validate Service Principal Name         Validate that a Service Principal Na... 
Cluster Configuration                   Validate Volume Consistency             If any volumes are flagged as incons... 
Hyper-V Configuration                   List Information About Servers Runni... List Hyper-V related information on ... 
Hyper-V Configuration                   Validate Compatibility of Virtual Fi... Validate that all specified nodes sh... 
Hyper-V Configuration                   Validate Hyper-V Memory Resource Poo... Validate that all specified nodes sh... 
Hyper-V Configuration                   Validate Hyper-V Network Resource Po... Validate that all specified nodes sh... 
Hyper-V Configuration                   Validate Hyper-V Processor Resource ... Validate that all specified nodes sh... 
Hyper-V Configuration                   Validate Hyper-V Role Installed         Validate that all the nodes have the... 
Hyper-V Configuration                   Validate Hyper-V Storage Resource Po... Validate that all specified nodes sh... 
Hyper-V Configuration                   Validate Matching Processor Manufact... Validate that all specified nodes sh... 
Hyper-V Configuration                   List Hyper-V Virtual Machine Informa... List Hyper-V virtual machine informa... 
Hyper-V Configuration                   Validate Hyper-V Integration Service... Validate that the Hyper-V integratio... 
Hyper-V Configuration                   Validate Hyper-V Virtual Machine Net... Validate that all virtual machines o... 
Hyper-V Configuration                   Validate Hyper-V Virtual Machine Sto... Validate that all virtual machines o... 
Inventory                               List Fibre Channel Host Bus Adapters    List Fibre Channel host bus adapters... 
Inventory                               List iSCSI Host Bus Adapters            List iSCSI host bus adapters on each... 
Inventory                               List SAS Host Bus Adapters              List Serial Attached SCSI (SAS) host... 
Inventory                               List BIOS Information                   List BIOS information from each node. 
Inventory                               List Environment Variables              List environment variables set on ea... 
Inventory                               List Memory Information                 List memory information for each node. 
Inventory                               List Operating System Information       List information about the operating... 
Inventory                               List Plug and Play Devices              List Plug and Play devices on each n... 
Inventory                               List Running Processes                  List the running processes on each n... 
Inventory                               List Services Information               List information about the services ... 
Inventory                               List Software Updates                   List software updates that have been... 
Inventory                               List System Drivers                     List the system drivers on each node. 
Inventory                               List System Information                 List system information such as comp... 
Inventory                               List Unsigned Drivers                   List the unsigned drivers on each node. 
Network                                 List Network Binding Order              List the order in which networks are... 
Network                                 Validate Cluster Network Configuration  Validate the cluster networks that w... 
Network                                 Validate IP Configuration               Validate that IP addresses are uniqu... 
Network                                 Validate Multiple Subnet Properties     For clusters using multiple subnets,... 
Network                                 Validate Network Communication          Validate that servers can communicat... 
Network                                 Validate Windows Firewall Configuration Validate that the Windows Firewall i... 
Storage                                 List Disks                              List all disks visible to one or mor... 
Storage                                 List Potential Cluster Disks            List disks that will be validated fo... 
Storage                                 Validate CSV Network Bindings           Validate that network bindings requi... 
Storage                                 Validate CSV Settings                   Validate that settings and configura... 
Storage                                 Validate Disk Access Latency            Validate acceptable latency for disk... 
Storage                                 Validate Disk Arbitration               Validate that a node that owns a dis... 
Storage                                 Validate Disk Failover                  Validate that a disk can fail over s... 
Storage                                 Validate File System                    Validate that the file system on dis... 
Storage                                 Validate Microsoft MPIO-based disks     Validate that disks that use Microso... 
Storage                                 Validate Multiple Arbitration           Validate that in a multiple-node arb... 
Storage                                 Validate SCSI device Vital Product D... Validate uniqueness of inquiry data ... 
Storage                                 Validate SCSI-3 Persistent Reservation  Validate that storage supports the S... 
Storage                                 Validate Simultaneous Failover          Validate that disks can fail over si... 
System Configuration                    Validate Active Directory Configuration Validate that all the nodes have the... 
System Configuration                    Validate All Drivers Signed             Validate that tested servers contain... 
System Configuration                    Validate Cluster Service and Driver ... Validate startup settings used by se... 
System Configuration                    Validate Memory Dump Settings           Validate that none of the nodes curr... 
System Configuration                    Validate Operating System Edition       Validate that all tested servers are... 
System Configuration                    Validate Operating System Installati... Validate that the operating systems ... 
System Configuration                    Validate Operating System Version       Validate that the operating systems ... 
System Configuration                    Validate Required Services              Validate that services required for ... 
System Configuration                    Validate Same Processor Architecture    Validate that all servers run as 64-... 
System Configuration                    Validate Service Pack Levels            Validate that all servers with same ... 
System Configuration                    Validate Software Update Levels         Validate that all tested servers hav... 
System Configuration                    Validate System Drive Variable          Validate that all nodes have the sam...
```

This example lists the names of all tests and categories in cluster validation.
Specify these test names with *Ignore* or *Include* parameters to run specific tests.

### Example 4: Validate specified nodes for storage
```
PS C:\> Test-Cluster -Node "node1", "node2" -Include "Storage"
Mode                LastWriteTime     Length Name 
----                -------------     ------ ---- 
-a---        10/10/2008   6:20 PM      37818 Test-Cluster on 2008.10.10 At 18.20.52.mht
```

This example runs the storage validation tests on the nodes named node1 and node2.
If either node1 or node2 is already a member of a cluster, then the tests will include all nodes in that cluster.

### Example 5: Validate specified nodes for everything except inventory
```
PS C:\> Test-Cluster -Node "node1", "node2" -Ignore Inventory
Mode                LastWriteTime     Length Name 
----                -------------     ------ ---- 
-a---        10/10/2008   6:20 PM     732889 Test-Cluster on 2008.10.10 At 18.19.47.mht
```

This example runs all validation tests except the Inventory tests on the nodes named node1 and node2.
If either node1 or node2 is already a member of a cluster, then the tests will include all nodes in that cluster.

### Example 6: Run a specific test
```
PS C:\> Test-Cluster -Include "List Potential Cluster Disks"
Mode                LastWriteTime     Length Name 
----                -------------     ------ ---- 
-a---        10/15/2008   2:58 PM      36119 Test-Cluster on 2008.10.15 At 14.58.44.mht
```

This example runs the test called List Potential Cluster Disks on the local cluster.

### Example 7: Run multiple tests
```
PS C:\> Test-Cluster -Include "List System Drivers","List Unsigned Drivers"
Mode                LastWriteTime     Length Name 
----                -------------     ------ ---- 
-a---        10/15/2008   3:00 PM     266571 Test-Cluster on 2008.10.15 At 15.00.08.mht
```

This example runs the tests called List System Drivers and List Unsigned Drivers on the local cluster.

## PARAMETERS

### -Cluster
Specifies the name of the cluster on which to run this cmdlet.
If the input for this parameter is `.` or it is omitted, then the cmdlet runs on the local cluster.

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

### -Disk
Specifies the disk number or disks for which to run the cmdlet.
If the specified disk is online and is assigned to a clustered role or Cluster Shared Volume, you must also specify the *Force* parameter to take the disk offline for the duration of the storage tests.
Otherwise, the specified disk must be offline before the cmdlet is run.
If the *Disk* parameter is not specified, storage tests run on all disks that are available for use in the cluster or that are in the cluster resource offline or failed state.
The acceptable values for this parameter are:

- Int32, Int64, Uint32, Uint64.
A number that represents a master boot record (MBR) signature of the disk. 
- **System.String**.
A string that represents a master boot record (MBR) signature of the disk, hexadecimal format is supported. 
- **System.String**.
A string that represents the GUID of a GPT disk. 
- **ClusterResource**.
A cluster resource object that represents a clustered disk. 
- **CimInstance#MSFT_Disk**.
An object returned from Get-Disk, from the Windows PowerShell® storage module.

```yaml
Type: Object[]
Parameter Sets: (All)
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ignore
Specifies which tests or category of tests to ignore during the validation test run.
All others tests or category of tests will run.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Include
Specifies which tests or category of tests to include during the validation test run.
Only the tests or category of tests specified here will run.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster on which to run the validation tests.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -List
Causes the cmdlet to list the tests and test categories.
No tests will run on the servers or cluster nodes.

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

### -Node
Specifies a comma-separated list of server names on which to run the cluster validation tests.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pool
Specifies the clustered storage pool or pools for which to run the cmdlet.
When the specified storage pool is online and a virtual disk in the storage pool is assigned to a clustered role or Cluster Shared Volume, you must also specify the **Force** parameter to take the storage pool offline for the duration of the storage tests.
Otherwise, the specified storage pool must be taken offline before the storage tests.
If the **Pool** parameter is not specified, storage tests run on all storage pools that are available for use in the cluster or that are in the cluster resource offline or failed state.
The acceptable values for this parameter are:

- **System.String**: A string that represents the name of the clustered storage pool or pools. 
- **ClusterResource**: A cluster resource object that represents a clustered storage pool. 
- **CimInstance#MSFT_StoragePool**: An object returned from **Get-StoragePool**, from the Windows PowerShell storage module.

```yaml
Type: Object[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportName
Specifies the name of the test report to generate.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### System.IO.FileInfo

### Microsoft.FailoverClusters.PowerShell.ClusterTestInfo

## NOTES

## RELATED LINKS

[Get-Cluster](./Get-Cluster.md)

[New-Cluster](./New-Cluster.md)

[Remove-Cluster](./Remove-Cluster.md)

[Start-Cluster](./Start-Cluster.md)

[Stop-Cluster](./Stop-Cluster.md)

