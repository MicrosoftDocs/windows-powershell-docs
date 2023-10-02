---
external help file: Microsoft.Assessments.WAS.PowerShell.dll-Help.xml
Module Name: WasPSExt
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/waspsext/get-wasimage?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WASImage
---

# Get-WASImage

## SYNOPSIS
Gets a list of images.

## SYNTAX

### ImageId
```
Get-WASImage [-ImageID] <Guid[]> [<CommonParameters>]
```

### ImageName
```
Get-WASImage [[-ImageName] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WASImage** cmdlet gets a list of the images that are available in the dep_nextref_was inventory.
Image metadata is also returned.

## EXAMPLES

### Example 1: Get all images
```
PS C:\>Get-WASImage
```

This command returns a list of all of the images in the dep_nextref_was inventory.

### Example 2: Get all images and output data to a table
```
PS C:\> Get-WASImage | format-table -property ImageName,OsVersion,Architecture,Language
```

This command returns a list of all of the images in the dep_nextref_was inventory, and formats the data in a table.

## PARAMETERS

### -ImageID
Specifies the ID of the image you want to get.
This is the image ID that is recorded in the dep_nextref_was inventory.
If this parameter is not specified, all images in the inventory are listed.

```yaml
Type: Guid[]
Parameter Sets: ImageId
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImageName
Specifies the name of the image that you want to get.
This is the image name recorded in the dep_nextref_was inventory.
The full name of the image isn't required.
Wildcards are accepted.
If this parameter isn't specified, all images in the inventory are listed.

```yaml
Type: String[]
Parameter Sets: ImageName
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Windows Assessment Services Technical Reference](https://go.microsoft.com/fwlink/?LinkId=215628)

[Update-WASJob](./Update-WASJob.md)

