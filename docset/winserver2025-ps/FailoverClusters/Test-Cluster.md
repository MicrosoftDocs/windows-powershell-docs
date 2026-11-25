---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/23/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/test-cluster?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Cluster
---

# Test-Cluster

## SYNOPSIS
Runs validation tests for failover cluster hardware and settings.

## SYNTAX

```
Test-Cluster [[-Node] <StringCollection>] [-Disk <Object[]>] [-Pool <Object[]>]
 [-ReportName <String>] [-List] [-Include <StringCollection>] [-Ignore <StringCollection>] [-Force]
 [-InputObject <PSObject>] [-Cluster <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Test-Cluster` cmdlet runs validation tests for failover cluster hardware and settings. Tests
can be run both before and after a cluster is set up.

Test results are captured in a file with the file name that you specify. By running the validation
tests, you can confirm that your hardware and settings are compatible with Failover Clustering.
There are multiple types of tests, including Cluster, Inventory, Network, Storage, System, and other
types of tests. Storage tests will not test online disks or storage pools that are in use by a
clustered role. To test such disks, first run `Stop-ClusterGroup` to stop the clustered role, and
then run `Test-Cluster`. After the tests are done, start the clustered roles, also known as resource
groups, again.

> [!NOTE]
> To perform some of the Cluster Shared Volume (CSV) validation tests, the `Test-Cluster` command
> creates a local user account named CliTest2 on each cluster node. The account is automatically
> removed from your system after the cluster validation tests are completed.

## EXAMPLES

### Example 1: Validate local cluster

```powershell
Test-Cluster
```

This example runs all applicable cluster validation tests on the local cluster.

### Example 2: Validate specified nodes

```powershell
Test-Cluster -Node "node1", "node2"
```

This example runs all cluster validation tests on the nodes named `node1` and `node2`. If either
`node1` or `node2` is already a member of a cluster, then the tests will include all nodes in that
cluster.

### Example 3: View tests and categories in cluster validation

```powershell
Test-Cluster -List
```

This example lists the names of all tests and categories in cluster validation. Specify these test
names with **Ignore** or **Include** parameters to run specific tests.

### Example 4: Validate specified nodes for storage

```powershell
Test-Cluster -Node "node1", "node2" -Include "Storage"
```

This example runs the storage validation tests on the nodes named node1 and node2. If either node1
or node2 is already a member of a cluster, then the tests will include all nodes in that cluster.

### Example 5: Validate specified nodes for everything except inventory

```powershell
Test-Cluster -Node "node1", "node2" -Ignore Inventory
```

This example runs all validation tests except the Inventory tests on the nodes named node1 and
node2. If either node1 or node2 is already a member of a cluster, then the tests will include all
nodes in that cluster.

### Example 6: Run a specific test

```powershell
Test-Cluster -Include "List Potential Cluster Disks"
```

This example runs the test called List Potential Cluster Disks on the local cluster.

### Example 7: Run multiple tests

```powershell
Test-Cluster -Include "List System Drivers","List Unsigned Drivers"
```

This example runs the tests called List System Drivers and List Unsigned Drivers on the local
cluster.

## PARAMETERS

### -Cluster

Specifies the name of the cluster on which to run this cmdlet. If the input for this parameter is
`.` or it is omitted, then the cmdlet runs on the local cluster.

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

Specifies the disk number or disks for which to run the cmdlet. If the specified disk is online and
is assigned to a clustered role or Cluster Shared Volume, you must also specify the **Force**
parameter to take the disk offline for the duration of the storage tests. Otherwise, the specified
disk must be offline before the cmdlet is run. If the **Disk** parameter isn't specified, storage
tests run on all disks that are available for use in the cluster or that are in the cluster resource
offline or failed state.

The acceptable values for this parameter are:

- **Int32, Int64, Uint32, or Uint64**. A number that represents a master boot record (MBR) signature of
  the disk.
- **System.String**. A string that represents a master boot record (MBR) signature of the disk,
  hexadecimal format is supported.
- **System.String**. A string that represents the GUID of a GPT disk.
- **ClusterResource**. A cluster resource object that represents a clustered disk.
- **CimInstance#MSFT_Disk**. An object returned from `Get-Disk`, from the Windows PowerShell storage
  module.

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

Runs the cmdlet without prompting for confirmation. By default the cmdlet will ask for confirmation
from the user before proceeding. When combined with the **Disk** or **Pool** parameters, the disks
or storage pool is taken offline for the duration of the storage tests.

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

Specifies which tests or category of tests to ignore during the validation test run. All other
tests or category of tests will run.

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

Specifies which tests or category of tests to include during the validation test run. Only the tests
or category of tests specified here will run.

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

Causes the cmdlet to list the tests and test categories. No tests will run on the servers or cluster
nodes.

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

Specifies the clustered storage pool or pools for which to run the cmdlet. When the specified
storage pool is online and a virtual disk in the storage pool is assigned to a clustered role or
Cluster Shared Volume, you must also specify the **Force** parameter to take the storage pool
offline for the duration of the storage tests. Otherwise, command will exit with an error. The
specified storage pool must be taken offline before running the storage tests. If the **Pool**
parameter isn't specified, storage tests run on all storage pools that are available for use in the
cluster or that are in the cluster resource offline or failed state.

The acceptable values for this parameter are:

- **System.String**: A string that represents the name of the clustered storage pool or pools.
- **ClusterResource**: A cluster resource object that represents a clustered storage pool.
- **CimInstance#MSFT_StoragePool**: An object returned from `Get-StoragePool`, from the Windows
  PowerShell storage module.

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

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

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
