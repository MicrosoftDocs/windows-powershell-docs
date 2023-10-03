---
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/get-hpcimage?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HpcImage
---

# Get-HpcImage

## SYNOPSIS
Gets operating system images for an HPC cluster.

## SYNTAX

```
Get-HpcImage [[-Name] <String[]>] [-WimFileName <String[]>] [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcImage** cmdlet gets one or more specified operating system images, or gets all of the operating system images in the image store for the HPC cluster.
You can specify the operating system images by name, or by the name of the Windows Image (.wim) file that contains the image.

## EXAMPLES

### Example 1: Get all operating system images
```
PS C:\>Get-HpcImage
```

This command gets all of the operating system images in the image store for the HPC cluster.

### Example 2: Get operating system images by name
```
PS C:\>Get-HpcImage -Name "My Test Image"
```

This command gets the operating system images that have a name of My Test Image.
Operating system images do not necessarily have unique names.

### Example 3: Get an operating system image by name and .wim file name
```
PS C:\>Get-HpcImage -Name "Image 01" -WimFileName "MyImages.wim"
```

This command gets the operating system image named Image 01 and that is in the MyImage.wim Windows image file.

## PARAMETERS

### -Name
Specifies an array of the names for the operating system images to get.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the images.
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

### -WimFileName
Specifies a list of the names of the .wim files that contain the operating system images to get.

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

### HpcImage
This cmdlet returns an array of **HpcImage** objects.

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Add-HpcImage](./Add-HpcImage.md)

[New-HpcImage](./New-HpcImage.md)

[Remove-HpcImage](./Remove-HpcImage.md)

[Replicate-HpcImage](./Replicate-HpcImage.md)
