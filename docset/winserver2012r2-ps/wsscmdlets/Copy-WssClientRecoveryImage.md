---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/copy-wssclientrecoveryimage?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-WssClientRecoveryImage
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

