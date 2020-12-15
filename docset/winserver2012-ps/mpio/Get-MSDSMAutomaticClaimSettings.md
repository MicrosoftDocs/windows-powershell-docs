---
external help file: MPIO_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 9860F832-453D-47AD-A396-294463818B72
manager: dansimp
---

# Get-MSDSMAutomaticClaimSettings

## SYNOPSIS
Gets the settings for MSDSM automatically claiming SAN disks for MPIO.

## SYNTAX

```
Get-MSDSMAutomaticClaimSettings
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

## INPUTS

### none

## OUTPUTS

### Cim.Instance

## NOTES

## RELATED LINKS

[Get-MSDSMSupportedHW](./Get-MSDSMSupportedHW.md)

[Disable-MSDSMAutomaticClaim](./Disable-MSDSMAutomaticClaim.md)

[Enable-MSDSMAutomaticClaim](./Enable-MSDSMAutomaticClaim.md)

