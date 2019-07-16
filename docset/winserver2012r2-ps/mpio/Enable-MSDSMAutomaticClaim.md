---
external help file: Mpio-help.xml
Module Name: MPIO
online version: 
schema: 2.0.0
title: Enable-MSDSMAutomaticClaim
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 8F71F9B3-68C3-4D0A-9D49-A6209B469015
ms.author: v-anbarr
ms.reviewer: brianlic
---

# Enable-MSDSMAutomaticClaim

## SYNOPSIS
Enables MSDSM to automatically claim SAN disks for MPIO.

## SYNTAX

```
Enable-MSDSMAutomaticClaim [-BusType] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Enable-MSDSMAutomaticClaim** cmdlet enables an Microsoft Device Specific Module (MSDSM) to automatically claim storage area network (SAN) disks for Microsoft Multipath I/O (MPIO) for a bus type.

You need to specify a valid bus type, either serial attached storage (SAS) and Internet Small Computer System Interface (iSCSI).
You can enable MSDSM to automatically claim both SAS and iSCSI disks.
Run the cmdlet twice, once for SAS, once for iSCSI.

## EXAMPLES

### Example 1: Enable automatic claims for iSCSI
```
PS C:\> Enable-MSDSMAutomaticClaim -BusType iSCSI
```

This command enables  MSDSM to automatically claim resources with an iSCSI bus type.
Specify SAS instead of iSCSI to enable for an SAS bus type.

## PARAMETERS

### -BusType
Specifies a bus type.
The cmdlet enables MSDSM to automatically SAN disks for this bus type.
The acceptable values for this parameter are: SAS and iSCSI.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: SAS, iSCSI

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

[Disable-MSDSMAutomaticClaim](./Disable-MSDSMAutomaticClaim.md)

[Get-MSDSMAutomaticClaimSettings](./Get-MSDSMAutomaticClaimSettings.md)

