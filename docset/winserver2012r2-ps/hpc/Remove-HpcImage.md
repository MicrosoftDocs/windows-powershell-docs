---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/remove-hpcimage?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-HpcImage
---

# Remove-HpcImage

## SYNOPSIS
Removes operating system images from the image store for an HPC cluster.

## SYNTAX

### Name (Default)
```
Remove-HpcImage [-WimFileName] <String[]> [-Scheduler <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Image
```
Remove-HpcImage -Image <HpcImage[]> [-Scheduler <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HpcImage** cmdlet removes one or more specified operating system images from the image store for the HPC cluster.
You can specify the operating system images by specifying **HpcImage** objects for the images or the names of the Windows Image (.wim) files that contain the images.

## EXAMPLES

### Example 1: Remove operating system images from the image store
```
PS C:\>Remove-HpcImage -WimFileName "MyImages.wim"
```

This command removes the operating system images that the MyImages.wim file contains from the image store for the HPC cluster.

### Example 2: Remove a specified operating system image from the image store
```
PS C:\>Get-HpcImage -Name "Image 01" -WimFileName "MyImages.wim" | Remove-HpcImage
```

This command gets an HPC image object for the operating system image named Image 01 in the MyImages.wim file, and removes that image from the image store for the HPC cluster.

## PARAMETERS

### -Image
Specifies an array of **HpcImage** objects that correspond to the operating system images that you want to remove.
Use the Get-HpcImage cmdlet to get the **HpcImage** objects for the operating system images.
You cannot specify both the *Image* and *WimFileName* parameters.

```yaml
Type: HpcImage[]
Parameter Sets: Image
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Specifies an array of names of the .wim files that contain the operating system images that you want to remove.
Use the Get-HpcImage cmdlet to view the names of the .wim files that contain the operating system images.
You cannot specify both the *WimFileName* and *Image* parameters.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcImage
This cmdlet returns an array of **HpcImage** objects.

## OUTPUTS

### None

## NOTES
* You cannot remove an operating system image if any node templates refer to the image or to other operating system images in the same .wim file as the image that you want to remove. If a .wim file contains multiple images, you cannot remove one of the images in the .wim file without removing the other images in the .wim file.
* The built-in ConfirmImpact setting for this cmdlet is Medium. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify `-Confirm:$False`. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify `-Confirm` or `-Confirm:$True`.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Add-HpcImage](./Add-HpcImage.md)

[Get-HpcImage](./Get-HpcImage.md)

[New-HpcImage](./New-HpcImage.md)

[Replicate-HpcImage](./Replicate-HpcImage.md)
