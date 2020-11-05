---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Add-HpcScsiStorageArray
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

# Add-HpcIScsiStorageArray

## SYNOPSIS
Adds the iSCSI storage array at the specified management IP address to an HPC cluster.

## SYNTAX

```
Add-HpcIScsiStorageArray -Name <String> -IpAddress <String> [-Description <String>]
[-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-HpcIScsiStorageArray** cmdlet adds the Internet SCSI (iSCSI) storage array at the specified management IP address to an HPC cluster.

An iSCSI storage array is a computer, storage system, or appliance that provides storage resources over a network connection by using the iSCSI protocol.
The nodes in an HPC cluster can use the iSCSI storage array to boot over a network connection, instead of requiring a local hard disk drive to serve as a system disk.

## EXAMPLES

### Example 1: Add an iSCSI storage array to an HPC cluster
```
PS C:\>Add-HpcIScsiStorageArray -Name "Storage Array 1" -IpAddress "10.0.0.10"
```

Adds the iSCSI storage array with a management IP address of 10.0.0.10 to the HPC cluster and assigns the name Storage Array 1 to that iSCSI storage array.

### Example 2: Add an iSCSI storage array and validate its connection
```
PS C:\>Add-HpcIScsiStorageArray -Name "Storage Array 2" -IpAddress "10.0.0.11" -Description "Second Storage Array" | Validate-HpcIScsiStorageArray
```

Adds the iSCSI storage array with a management IP address of 10.0.0.11 to the HPC cluster and assigns the name Storage Array 2 and the description "Second Storage Array" to that iSCSI storage array.
This example then redirects the **HpcIScsiStorageArray** object that is the output of the **Add-HpcIScsiStorageArray** cmdlet to become input to the Validate-HpcIScsiStorageArray cmdlet.
This validates that the head node for the HPC cluster can connect to the iSCSI storage array.

## PARAMETERS

### -Description
Specifies a description of the iSCSI storage array that you want to add to the HPC cluster.

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

### -IpAddress
Specifies the management IP address for the iSCSI storage array that you want to add to the HPC cluster.

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

### -Name
Specifies a name for the iSCSI storage array that you want to add to the HPC cluster.
The maximum length of the name is 400 characters.

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
Specifies the host name or IP address of the head node for the cluster to which you want to add the iSCSI storage array.
The value must be a valid computer name or IP address.
If you do not specify the Scheduler parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.
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

### None

## OUTPUTS

### HpcIScsiStorageArray

## NOTES
* The name and management IP address for the iSCSI storage array must be unique for the HPC cluster. If you try to add an iSCSI storage array with a name or management IP address that another iSCSI storage array for the cluster already uses, an error occurs.
* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet was introduced in HPC Pack 2008 R2. It is not supported in previous versions.

## RELATED LINKS

[Get-HpcIScsiStorageArray](./Get-HpcIScsiStorageArray.md)

[Remove-HpcIScsiStorageArray](./Remove-HpcIScsiStorageArray.md)

[Set-HpcIScsiStorageArray](./Set-HpcIScsiStorageArray.md)

[Validate-HpcIScsiStorageArray](./Validate-HpcIScsiStorageArray.md)
