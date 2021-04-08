---
author: Kateyanne
external help file: MPIO_Cmdlets.xml
manager: dansimp
Module Name: MPIO
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/mpio/disable-msdsmautomaticclaim?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Disable-MSDSMAutomaticClaim

## SYNOPSIS
Stops MSDSM from automatically claiming SAN disks for MPIO for a bus type.

## SYNTAX

```
Disable-MSDSMAutomaticClaim [-BusType] <String>
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

[Enable-MSDSMAutomaticClaim](./Enable-MSDSMAutomaticClaim.md)

[Get-MSDSMAutomaticClaimSettings](./Get-MSDSMAutomaticClaimSettings.md)

