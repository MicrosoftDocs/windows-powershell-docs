---
external help file: WasPsExt_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 03708C21-87A9-44BB-A015-0FA2DA14869D
manager: dansimp
---

# Get-WASImage

## SYNOPSIS
Gets a list of images.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-WASImage [-ImageID] <Guid[]>
```

### UNNAMED_PARAMETER_SET_2
```
Get-WASImage [[-ImageName] <String[]>]
```

## DESCRIPTION
The **Get-WASImage** cmdlet gets a list of the images that are available in the Windows Assessment Services inventory.
Image metadata is also returned.

## EXAMPLES

### Example 1: Get all images
```
PS C:\>Get-WASImage
```

This command returns a list of all of the images in the Windows Assessment Services inventory.

### Example 2: Get all images and output data to a table
```
PS C:\> Get-WASImage | format-table -property ImageName,OsVersion,Architecture,Language
```

This command returns a list of all of the images in the Windows Assessment Services inventory, and formats the data in a table.

## PARAMETERS

### -ImageID
Specifies the ID of the image you want to get.
This is the image ID that is recorded in the Windows Assessment Services inventory.
If this parameter is not specified, all images in the inventory are listed.

```yaml
Type: Guid[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImageName
Specifies the name of the image that you want to get.
This is the image name recorded in the Windows Assessment Services inventory.
The full name of the image isn't required.
Wildcards are accepted.
If this parameter isn't specified, all images in the inventory are listed.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Windows Assessment Services Technical Reference](http://go.microsoft.com/fwlink/?LinkId=215628)

[Update-WASJob](./Update-WASJob.md)

