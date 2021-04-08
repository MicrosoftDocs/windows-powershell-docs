---
author: Kateyanne
description: 
external help file: Mpio-help.xml
manager: jasgro
Module Name: MPIO
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/mpio/get-msdsmautomaticclaimsettings?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-MSDSMAutomaticClaimSettings
---

# Get-MSDSMAutomaticClaimSettings

## SYNOPSIS
Gets the settings for MSDSM automatically claiming SAN disks for MPIO.

## SYNTAX

```
Get-MSDSMAutomaticClaimSettings [<CommonParameters>]
```

## DESCRIPTION
The **Get-MSDSMAutomaticClaimSettings** cmdlet gets the settings for a Microsoft Device Specific Module (MSDSM) automatically claiming storage area network (SAN) disks for Microsoft Multipath I/O (MPIO).

MSDSM can automatically claim serial attached storage (SAS) or Internet Small Computer System Interface (iSCSI) or both or neither.
Use the **Enable-MSDSMAutomaticClaim** cmdlet or the **Disable-MSDSMAutomaticClaim** cmdlet to change the settings.

## EXAMPLES

### Example 1: Get automatic claim settings
```
PS C:\> Get-MSDSMAutomaticClaimSettings 
Name                            Value

----                            -----

iSCSI                           False

SAS                             True
```

This command gets the automatic claim settings for MSDSM.
In this instance, MSDSM automatically claims SAS disks, but not iSCSI disks.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### none

## OUTPUTS

### Cim.Instance

## NOTES

## RELATED LINKS

[Get-MSDSMSupportedHW](./Get-MSDSMSupportedHW.md)

[Disable-MSDSMAutomaticClaim](./Disable-MSDSMAutomaticClaim.md)

[Enable-MSDSMAutomaticClaim](./Enable-MSDSMAutomaticClaim.md)

