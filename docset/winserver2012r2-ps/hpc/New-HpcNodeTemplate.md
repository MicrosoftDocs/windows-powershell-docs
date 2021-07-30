---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/new-hpcnodetemplate?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-HpcNodeTemplate
---

# New-HpcNodeTemplate

## SYNOPSIS
Creates a node template and optionally associates an operating system image with the node template.

## SYNTAX

### NoImage (Default)
```
New-HpcNodeTemplate [-Name] <String> [-Description <String>] [-UpdateCategory <UpdateCategory>]
 [-UpdateName <String[]>] [-Type <InstallHpcType>]
 [-Scheduler <String[]>] [<CommonParameters>]
```

### Image
```
New-HpcNodeTemplate [-Name] <String> [-Description <String>] -Image <HpcImage> [-Multicast]
 [-ProductKey <String>] [-AdminCredential <PSCredential>] [-ConfirmPassword] [-UpdateCategory <UpdateCategory>]
 [-UpdateName <String[]>] [-Type <InstallHpcType>]
 [-Scheduler <String[]>] [<CommonParameters>]
```

### Name
```
New-HpcNodeTemplate [-Name] <String> [-Description <String>] -ImageName <String> [-WimFileName <String>]
 [-Multicast] [-ProductKey <String>] [-AdminCredential <PSCredential>] [-ConfirmPassword]
 [-UpdateCategory <UpdateCategory>] [-UpdateName <String[]>] [-Type <InstallHpcType>]
 [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **New-HpcNodeTemplate** cmdlet creates a node template, and optionally associates an operating system image with the node template.

## EXAMPLES

### Example 1: Create a broker node template
```
PS C:\>New-HpcNodeTemplate -Name "MyNodeTemplate" -Type BrokerNode
```

This command creates a node template for broker nodes named MyNodeTemplate.

### Example 2: Create a node template and add a description
```
PS C:\>New-HpcNodeTemplate -Name "TestNodeTemplate" -Description "Template for testing."
```

This command creates a node template named TestNodeTemplate and has a description of "Template for testing."

### Example 3: Create a node template and associate it with an operating system image
```
PS C:\>New-HpcNodeTemplate -Name "NodeTemplate1" -ImageName "MyImage" -Multicast -ProductKey "12345-67890-ABCDE-FGHIJ-KLMNO"
```

This command creates a node template named NodeTemplate1 and associates the operating system image named MyImage with the node template.
This example also specifies that the deployment process should multicast the operating system image, and specifies a product key for activating the operating system.
This example requires that the HPC cluster has only one image named MyImage.

### Example 4: Create a node template, associate it with an operating system image, and specify which updates to apply
```
PS C:\>New-HpcNodeTemplate -Name "NodeTemplate2" -ImageName "MyImage" -WimFileName "MyImages.wim" -UpdateCategory Critical
```

This command creates a node template named NodeTemplate2 and associates the operating system image named MyImage from the Windows Image (.wim) file named MyImages.wim with the node template.
This example also specifies that only critical updates should be applied when you deploy or update nodes that are associated with the node template.

## PARAMETERS

### -AdminCredential
Specifies a **PSCredential** object for the administrator credential that you want to use when you deploy the node, if you do not want to use an automatically generated credential.
Use the Get-Credential cmdlet to get a **PSCredential** object.

The user name for this credential must be Administrator.
You can only specify this parameter if you specified an image for the node template by specifying the Image or *ImageName* parameter.
If you do not specify the *AdminCredential* parameter when you specify an image for the node template, the **New-HpcNodeTemplate** cmdlet automatically generates the credentials and password for the Administrator.

```yaml
Type: PSCredential
Parameter Sets: Image, Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description to use for the node template.

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

### -Image
Specifies an **HpcImage** object for the operating system image that you want to associate with the new node template.
When you deploy a compute node with the node template, the deployment process installs the operating system from this image.
Use the Get-HpcImage cmdlet to get an **HpcImage** object for an operating system image.
You cannot specify the *Image* parameter if you specify the *ImageName* parameter or both the *ImageName* and *WimFileName* parameters.

```yaml
Type: HpcImage
Parameter Sets: Image
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ImageName
Specifies the name of the operating system image that you want to associate with the new node template.
When you deploy a compute node with the node template, the deployment process installs the operating system from this image.
Use the Get-HpcImage cmdlet to view the names of the available operating system images.

You cannot specify both the *ImageName* and *Image* parameters.
If you specify a name for the *ImageName* parameter that multiple Windows Image (.wim) files share, you must also specify the name of the .wim file with the *WimFileName* parameter.

```yaml
Type: String
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Multicast
Indicates that this operation multicasts the operating system image during the deployment of nodes that are associated with the new node template.
You can only specify the *Multicast* parameter if you also specify the *Image* or *ImageName* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: Image, Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name to use for the new node template.
The maximum length of the name is 250 characters.

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

### -ProductKey
Specifies a product key to use to activate the operating system on nodes that are associated with the node template.
The format of the product key consists of five groups of five alphanumeric characters separated by hyphens (-).
You can specify the *ProductKey* parameter only if you also specify the *Image* or the *ImageName* parameter.

```yaml
Type: String
Parameter Sets: Image, Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster to which you want to add the node template.
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

### -Type
Specifies the type of node to which the node template should apply.
The acceptable values for this parameter are:

- BrokerNode
- ComputeNode
- WorkstationNode

This parameter was introduced in HPC Pack 2008 R2.
It is not available in previous versions.

```yaml
Type: InstallHpcType
Parameter Sets: (All)
Aliases:
Accepted values: BrokerNode, ComputeNode, WorkstationNode

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateCategory
Specifies the category of updates to apply when you update or deploy a node that is associated with the node template.
Valid values are:

- All
- Critical
- None

Specify All to apply all updates, Critical to apply only critical updates, or None to not apply updates.

```yaml
Type: UpdateCategory
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateName
Specifies an array of the names of updates to apply when you update or deploy a node that is associated with the node template.
Specify each of the updates by using the Microsoft Knowledge Base number for the update.

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
Specifies the name of the Windows Image (.wim) file that contains the image.
You cannot specify both the *WimFileName* and *Image* parameters.
If you specify the *WinFileName* parameter, you must also specify the *ImageName* parameter.

```yaml
Type: String
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfirmPassword
Indicates whether to prompt the user for the administrator password when deploying the node.
A nonzero value or $True prompts the user for the administrator password that you want to use when deploying the node.
A value of 0 or $False does not prompt the user for the administrator password that you want to use when deploying the node.

This parameter was introduced in HPC Pack 2008 R2.
It is not available in previous versions.

```yaml
Type: SwitchParameter
Parameter Sets: Image, Name
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

### HpcImage

## OUTPUTS

### HpcNodeTemplate

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Assign-HpcNodeTemplate](./Assign-HpcNodeTemplate.md)

[Copy-HpcNodeTemplate](./Copy-HpcNodeTemplate.md)

[Get-HpcImage](./Get-HpcImage.md)

[Export-HpcNodeTemplate](./Export-HpcNodeTemplate.md)

[Import-HpcNodeTemplate](./Import-HpcNodeTemplate.md)

[Remove-HpcNodeTemplate](./Remove-HpcNodeTemplate.md)
