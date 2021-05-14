---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/new-hpcimage?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-HpcImage
---

# New-HpcImage

## SYNOPSIS
Creates an operating system image and adds it to the image store for an HPC cluster.

## SYNTAX

### Media
```
New-HpcImage [-WimFileName] <String> [-Path <String>] [<CommonParameters>]
```

### Node
```
New-HpcImage [-WimFileName] <String> [-TargetNodeName <String>]
 [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **New-HpcImage** cmdlet creates an operating system image from the installation directory or installation media for the operating system or from the operating system on the specified node, and then adds the image to the image store for an HPC cluster.

## EXAMPLES

### Example 1: Create a system image from installation media
```
PS C:\>New-HpcImage -Path "D:\ -WimFileName NewImage.wim"
```

This command creates an operating system image from the installation media in drive D, and then saves the image in the NewImage.wim file.
This example assumes that the root directory of the installation media contains the Setup.exe file for installing the operating system.

### Example 2: Create a system image from a specified node
```
PS C:\>New-HpcImage -TargetNodeName "ComputeNode01" -WimFileName "ComputeNode.wim"
```

This command creates a new operating system image from the node named ComputeNode01, and then saves the image in the ComputeNode.wim file.

## PARAMETERS

### -Path
Specifies the directory in the installation media or installation folder that contains the Setup.exe file for installing the operating system.
The **New-HpcImage** cmdlet generates the operating system image from the data at this location.

```yaml
Type: String
Parameter Sets: Media
Aliases:

Required: False
Position: Named
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

### -TargetNodeName
Specifies the name of the node from which you want to create the operating system image.
The node must be in the Offline state before you can create an image from it.
Use the Set-HpcNodeState cmdlet to take a node offline.

This parameter was introduced in HPC Pack 2008 R2.
It is not available in previous versions.

```yaml
Type: String
Parameter Sets: Node
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WimFileName
Specifies the name of the Windows Image (.wim) file to create.
One .wim file can contain multiple images.
An error occurs if you specify a .wim file that already exists in the image store for the HPC cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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
* The **New-HpcImage** cmdlet creates a.wim file for the operating system image, and then saves it in the Data\InstallShare\Images subfolder of the installation folder for HPC Pack.

  If you already have an operating system image in a .wim file, use the Add-HpcImage cmdlet to add the image to the image store for the HPC cluster.

* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Add-HpcImage](./Add-HpcImage.md)

[Get-HpcImage](./Get-HpcImage.md)

[Remove-HpcImage](./Remove-HpcImage.md)

[Replicate-HpcImage](./Replicate-HpcImage.md)

[Set-HpcNodeState](./Set-HpcNodeState.md)
