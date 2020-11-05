---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Remove-HpcIScsiStorageArray
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

# Remove-HpcIScsiStorageArray

## SYNOPSIS
Removes the specified iSCSI storage array from the HPC cluster.

## SYNTAX

```
Remove-HpcIScsiStorageArray -HpcIScsiStorageArray <HpcIScsiStorageArray>
[-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HpcIScsiStorageArray** cmdlet removes the specified Internet SCSI (iSCSI) storage array from the HPC cluster.
You can only remove an iSCSI storage array from the HPC cluster if no nodes are currently deployed with the iSCSI storage array.

## EXAMPLES

### Example 1: Remove an iSCSI storage array by management IP address
```
PS C:\>Get-HpcIScsiStorageArray -IpAddresses "10.0.0.10" | Remove-HpcIScsiStorageArray
```

This command gets an **HpcIScsiStorageArray** object for the iSCSI storage array that has a management IP address of 10.0.0.10, and then redirects this object as input to the **Remove-HpcIScsiStorageArray** cmdlet to remove the storage array from the HPC cluster.

### Example 2: Get an iSCSI storage array and remove it
```
PS C:\>$SA = Get-HpcIScsiStorageArray -IpAddresses "10.0.0.11"
PS C:\> Remove-HpcIScsiStorageArray -HpcIScsiStorageArray $SA
```

This command gets an **HpcIScsiStorageArray** object for the iSCSI storage array that has a management IP address of 10.0.0.11, and then stores the object in the variable $SA.

The second command removes the iSCSI storage array stored in $SA from the HPC cluster.

## PARAMETERS

### -HpcIScsiStorageArray
Specifies the iSCSI storage array that you want to remove from the HPC cluster.
Use the Get-HpcIScsiStorageArray cmdlet to get an **HpcIScsiStorageArray** object for an iSCSI storage array in the HPC cluster.

```yaml
Type: HpcIScsiStorageArray
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the HPC cluster that contains the iSCSI storage array that you want to remove.
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

### HpcIScsiStorageArray

## OUTPUTS

### None

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet was introduced in HPC Pack 2008 R2. It is not available in previous versions.

## RELATED LINKS

[Add-HpcIScsiStorageArray](./Add-HpcIScsiStorageArray.md)

[Get-HpcIScsiStorageArray](./Get-HpcIScsiStorageArray.md)

[Set-HpcIScsiStorageArray](./Set-HpcIScsiStorageArray.md)

[Validate-HpcIScsiStorageArray](./Validate-HpcIScsiStorageArray.md)
