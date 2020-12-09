---
external help file: Mpio-help.xml
Module Name: MPIO
online version: 
schema: 2.0.0
title: Disable-MSDSMAutomaticClaim
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 18902AAE-5A6D-4E05-99AA-9B6AC326A97E
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Disable-MSDSMAutomaticClaim

## SYNOPSIS
Stops MSDSM from automatically claiming SAN disks for MPIO for a bus type.

## SYNTAX

```
Disable-MSDSMAutomaticClaim [-BusType] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Disable-MSDSMAutomaticClaim** cmdlet stops a Microsoft Device Specific Module (MSDSM) from automatically claiming storage area network (SAN) disks for Microsoft Multipath I/O (MPIO) for a specified bus type.

The valid bus types are serial attached storage (SAS) and Internet Small Computer System Interface (iSCSI).
This cmdlet does not change previously claimed SAN disks.

## EXAMPLES

### Example 1: Disable automatic claim for iSCSI
```
PS C:\> Disable-MSDSMAutomaticClaimSettings -BusType iSCSI
```

This command stops MSDSM from automatically claiming SAN disks for MPIO for iSCSI bus types.
The command does not affect previously claimed disks.

The command does not affect the settings for an SAS bus type.
If you want to disable automatic claims for both bus types, use the cmdlet again and specify SAS.

## PARAMETERS

### -BusType
Specifies a bus type.
This cmdlet disables automatic claiming of SAN disks for this bus type.
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

[Enable-MSDSMAutomaticClaim](./Enable-MSDSMAutomaticClaim.md)

[Get-MSDSMAutomaticClaimSettings](./Get-MSDSMAutomaticClaimSettings.md)

