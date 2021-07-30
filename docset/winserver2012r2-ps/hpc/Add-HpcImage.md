---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/add-hpcimage?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-HpcImage
---

# Add-HpcImage

## SYNOPSIS
Adds an operating system image to the image store for an HPC cluster.

## SYNTAX

```
Add-HpcImage [-Path] <String[]> [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-HpcImage** cmdlet loads one or more specified Windows image (.wim) files, and adds the operating system images from those files to the image store for an HPC cluster.

## EXAMPLES

### Example 1: Add operating system images to an image store
```
PS C:\>Add-HpcImage -Path "C:\MyImages\ImageFile1.wim" -Scheduler "172.25.212.201"
```

This command loads the operating system images from the file at C:\MyImages\ImageFile1.wim, and adds them to the image store for the HPC cluster that has a head node with an IP address of 172.25.212.201.

## PARAMETERS

### -Path
Specifies an array of file names and paths for the .wim files from which you want to load the operating system images.
A .wim file can contain more than one image, and the **Add-HpcImage** cmdlet adds all of the images in the .wim file to the image store for the HPC cluster.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster to which you want to add the images.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### HpcImage[]

## NOTES
* Use the New-HpcImage cmdlet instead of the **Add-HpcImage** cmdlet if you do not already have a .wim file, but want to create a .wim file from the installation files for the operating system, and then add the operating system images in that new .wim file to the image store for the HPC cluster.

  The **Add-HpcImage** cmdlet saves a copy of the .wim files in the Data\InstallShare\Images subfolder of the installation folder for Microsoft HPC Pack.

* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcImage](./Get-HpcImage.md)

[New-HpcImage](./New-HpcImage.md)

[Remove-HpcImage](./Remove-HpcImage.md)

[Replicate-HpcImage](./Replicate-HpcImage.md)
