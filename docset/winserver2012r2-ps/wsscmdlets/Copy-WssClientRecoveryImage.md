---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Copy-WssClientRecoveryImage
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: A4B221E3-618D-4C48-9983-AFD3974E0A36
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Copy-WssClientRecoveryImage

## SYNOPSIS
Copies files needed to build a client recovery image to a USB device.

## SYNTAX

```
Copy-WssClientRecoveryImage [-Target] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Copy-WssClientRecoveryImage** cmdlet copies files needed to build a client recovery image to a USB device.
Specify the partition for the device.

Before you use this cmdlet, use the DiskPart utility to clean the USB device, create a primary partition, format that partition as NTFS, and activate the partition.
For more information about the DiskPart utility, see DiskParthttp://technet.microsoft.com/en-us/library/cc770877.aspx (http://technet.microsoft.com/en-us/library/cc770877.aspx).

## EXAMPLES

### Example 1: Copy client recovery image
```
PS C:\> Copy-WssClientRecoveryImage -Target "F:"
```

This command copies necessary files to the USB device specified as F:.
Before you begin, use the DiskPart utility to prepare the device.

## PARAMETERS

### -Target
Specifies the target partition.
The cmdlet copies the image to the root folder of the specified location.
Specify the target partition by drive letter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

