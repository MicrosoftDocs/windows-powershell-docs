---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 07D67763-DB64-47D6-ADA2-BADD3714A4F8
manager: dansimp
---

# Get-WssMountVhd

## SYNOPSIS
Gets a collection of VHDs from a backup set.

## SYNTAX

```
Get-WssMountVhd [-BackupSet] <BackupSet>
```

## DESCRIPTION
The **Get-WssMountVhd** cmdlet gets a collection of virtual hard drives (VHDs) from a backup set.
Each VHD represents a backup volume in the set.

## EXAMPLES

### Example 1: Get VHDs from a backup set
```
PS C:\> $ContosoBUSet25VHD = Get-WssMountVhd -BackupSet $ContosoBUSet25
```

This example gets the VHD collection from the backup set that is stored in the variable named $ContosoBUSet25 and stores the collection in the variable named $ContosoBUSet25VHD.

## PARAMETERS

### -BackupSet
Specifies the backup set from which to get the collection of VHDs.

```yaml
Type: BackupSet
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Select-WssMountVhd](./Select-WssMountVhd.md)

