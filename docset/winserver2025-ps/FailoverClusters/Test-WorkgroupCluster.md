---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.Adless.PowerShell.psm1-help.xml
Module Name: FailoverClusters
ms.date: 09/11/2024
online version: https://learn.microsoft.com/powershell/module/failoverclusters/test-workgroupcluster?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-WorkgroupCluster
---

# Test-WorkgroupCluster

## SYNOPSIS
Tests the configuration of a workgroup cluster.

## SYNTAX

```
Test-WorkgroupCluster [[-Node] <String[]>] [[-Credentials] <PSCredential[]>] [[-Disk] <Object[]>]
 [[-Pool] <Object[]>] [[-ReportName] <String>] [[-Include] <String[]>] [[-Ignore] <String[]>]
 [-Force] [[-Cluster] <String>] [-Confirm] [-WhatIf] [-Destination] <String> [<CommonParameters>]
```

## DESCRIPTION

The `Test-WorkgroupCluster` function tests the configuration of a workgroup cluster. The rest of
the parameters will be forwarded to the `Test-Cluster` function. Please refer to the documentation
for the [Test-Cluster](/powershell/module/failoverclusters/test-cluster) cmdlet.

## EXAMPLES

### EXAMPLE 1

```powershell
Test-WorkgroupCluster -Node "Node1", "Node2" -Credentials $cred1, $cred2
```

This example tests the configuration of a workgroup cluster with `Node1` and `Node2` using the
credentials in `$cred1` and `$cred2`, and additional parameters.

## PARAMETERS

### -Node

An array of nodes in the workgroup cluster.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: @()
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credentials

An array of credentials for the nodes.

```yaml
Type: PSCredential[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Disk

Specifies the disk number or disks for which to run the cmdlet. If the specified disk is online and
is assigned to a clustered role or Cluster Shared Volume, you must also specify the **Force**
parameter to take the disk offline for the duration of the storage tests. Otherwise, the specified
disk must be offline before the cmdlet is run.

If the **Disk** parameter isn't specified, storage tests run on all disks that are available for
use in the cluster or that are in the cluster resource offline or failed state.

Acceptable values are:

- **Int32, Int64, Uint32, or Uint64**: A number that represents a master boot record (MBR)
  signature of the disk.
- **System.String**: A string that represents a master boot record (MBR) signature of the disk,
  hexadecimal format is supported, or a string that represents the GUID of a GPT disk.
- **ClusterResource**: A cluster resource object that represents a clustered disk.
- **CimInstance#MSFT_Disk**: An object returned from `Get-Disk`, from the Windows PowerShell storage
  module.

```yaml
Type: Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pool

Specifies the clustered storage pool or pools for which to run the cmdlet. When the specified
storage pool is online and a virtual disk in the storage pool is assigned to a clustered role or
Cluster Shared Volume, you must also specify the **Force** parameter to take the storage pool
offline for the duration of the storage tests. Otherwise, the command will exit with an error.

The specified storage pool must be taken offline before running the storage tests. If the **Pool**
parameter isn't specified, storage tests run on all storage pools that are available for use in the
cluster or that are in the cluster resource offline or failed state.

Acceptable values are:

- **System.String**: A string that represents the name of the clustered storage pool or pools.
- **ClusterResource**: A cluster resource object that represents a clustered storage pool.
- **CimInstance#MSFT_StoragePool**: An object returned from `Get-StoragePool`, from the Windows
  PowerShell storage module.

```yaml
Type: Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
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
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Include

Specifies which tests or category of tests to include during the validation test run. Only the tests
or category of tests specified will run.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ignore

Specifies which tests or category of tests to ignore during the validation test run. All other
tests or category of tests will run.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
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
Position: 9
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cluster

Specifies the name of the cluster on which to run this cmdlet. If the input for this parameter is
`.` or it is omitted, then the cmdlet runs on the local cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 10
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 11
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 12
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Destination

Specifies the location to which to copy one or more cluster logs. To copy to the current folder, use
`.` for this parameter input. Default location is `C:\Windows\Cluster\Reports`.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 13
Default value: (Get-Location).Path
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WorkgroupClusterNode](add-workgroupclusternode.md)

[New-WorkgroupCluster](new-workgroupcluster.md)

[Remove-WorkgroupCluster](remove-workgroupcluster.md)

[Remove-WorkgroupClusterNode](remove-workgroupclusternode.md)

[Set-WorkgroupClusterRemotingConfiguration](set-workgroupclusterremotingconfiguration.md)

[Test-WorkgroupClusterRemoting](test-workgroupclusterremoting.md)
