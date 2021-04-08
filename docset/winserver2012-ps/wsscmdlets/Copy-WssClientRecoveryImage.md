---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/copy-wssclientrecoveryimage?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Copy-WssClientRecoveryImage

## SYNOPSIS
Copies files needed to build a client recovery image to a USB device.

## SYNTAX

```
Copy-WssClientRecoveryImage [-Target] <String>
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
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

