---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/replicate-hpcimage?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Replicate-HpcImage
---

# Replicate-HpcImage

## SYNOPSIS
Copies a base-node operating system image from a Windows image (.wim) file to an Internet SCSI (iSCSI) storage array.

## SYNTAX

```
Replicate-HpcImage -WimFileName <String> -StorageArrays <HpcIScsiStorageArray[] [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Replicate-HpcImage** cmdlet copies the base-node operating system image from the specified Windows image (.wim) file to the specified iSCSI storage array.

## EXAMPLES

### Example 1: Replicate an operating system image to a storage array
```
PS C:\>$SA = Get-HpcIScsiStorageArray -IpAddresses 10.0.0.11
PS C:\> Replicate-HpcImage -StorageArray $SA -WimFileName "iSCSI Base Image.wim"
```

The first command gets an **HpcIScsiStorageArray** object for the storage array with an IP address of 10.0.0.11, and then stores that object in the $SA variable.

The second command copies the image specified in the iSCSI Base Image.wim file to the storage array in $SA.

### Example 2: Replicate an operating system to multiple storage arrays
```
PS C:\>$SA_All = Get-HpcIScsiStorageArray
PS C:\> Replicate-HpcImage -StorageArray $SA_All -WimFileName "iSCSI Base Image.wim"
```

The first command gets all of the storage arrays for the cluster, and then stores them in the $SA_All variable.

The second command copies the image specified in the iSCSI Base Image.wim file to the storage arrays in $SA_All.

## PARAMETERS

### -Scheduler
Specifies the host name or IP address of the head node of the HPC cluster that contains the storage arrays to which you want to copy the operating system image and the image that you want to copy.
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

### -StorageArrays
Specifies the storage arrays to which you want to copy the operating system image.

Use the Get-HpcIScsiStorageArray cmdlet to get the **HpcIScsiStorageArray** objects for one or more storage arrays and save them to a variable, and then specify that variable with this parameter.

```yaml
Type: HpcIScsiStorageArray[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WimFileName
Specifies the name of the Windows image (.wim) file that contains the operating system image that you want to copy to the storage arrays.

Use the Get-HpcImage cmdlet to see the images and their corresponding .wim files that are available for the cluster.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES
* The replication process can take a long time to complete, so this cmdlet can take a long time to run.
* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet was introduced in HPC Pack 2008 R2. It is not supported in previous versions.

## RELATED LINKS

[Add-HpcImage](./Add-HpcImage.md)

[Get-HpcImage](./Get-HpcImage.md)

[Get-HpcIScsiStorageArray](./Get-HpcIScsiStorageArray.md)

[New-HpcImage](./New-HpcImage.md)

[Remove-HpcImage](./Remove-HpcImage.md)
