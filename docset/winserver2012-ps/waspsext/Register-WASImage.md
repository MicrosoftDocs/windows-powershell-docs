---
author: Kateyanne
external help file: WasPsExt_Cmdlets.xml
manager: dansimp
Module Name: WasPSExt
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/waspsext/register-wasimage?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Register-WASImage

## SYNOPSIS
Imports an image into inventory.

## SYNTAX

```
Register-WASImage [-ImagePath] <String> [[-ImageName] <String>] [[-ImageType] <String>]
 [[-DeploymentInfo] <String>] [[-UnattendPath] <String>]
```

## DESCRIPTION
The **Register-WASImage** cmdlet imports images (specifically its metadata) into the Windows Assessment Services inventory.
The image that is being imported must be in the \relax\images share on the Windows Assessment Services server.
By default, the cmdlet assumes images are .wim files and imports all images in the WIM file.
If you are not using the WIM image format, you must specify the image type.
The **ImagePath** parameter is required.

## EXAMPLES

### Example 1
```
PS C:\>Register-WasImage -ImagePath 'C:\relax\images\WasTestImage.wim' -ImageName 'Windows Test Image' -ImageType 'wim' -DeploymentInfo 'imageindex=1'
```

Imports the image with index 1 in the WasTestImage.wim, from the \relax\images\ share, into the Windows Assessment Services inventory.

## PARAMETERS

### -DeploymentInfo
Specifies a deployment solution other than Windows Assessment Services.
This parameter is ignored if the **ImagePath** parameter points to a WIM file.
The format of the string is dictated by the alternative deployment solution you choose.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImageName
Specifies the name of the image that you want to import.
The full name of the image is required.
Wildcards aren't accepted.
If this parameter isn't specified, all images are imported.
To get the name of the image inside the WIM file, use the **DISM Get-Image** command.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImagePath
Specifies the path to the image file you want to register.
This must be the full path to the image, using the fully qualified domain name of the server.
This parameter is required.

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

### -ImageType
Specifies the type of image you want to import, if you are not using a WIM file.
By default the only image type supported is WIM.
For more information about using custom image types, see the Windows Assessment Services documentation.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UnattendPath
Specifies the path to the unattended answer file.
These files must be stored in the \relax\unattendfiles share on the Windows Assessment Services server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Windows Assessment Services Technical Reference](https://go.microsoft.com/fwlink/?LinkId=215628)

