---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: C2471CFF-73E2-4296-8DE8-B27A8F5FB9CB
manager: dansimp
---

# Get-WssSpacesPool

## SYNOPSIS
Retrieves a storage pool, or all storage pools in the system.

## SYNTAX

```
Get-WssSpacesPool [-ID <String>]
```

## DESCRIPTION
The **Get-WssSpacesPool** cmdlet retrieves a storage pool in sbs_sbs8_2, or all storage pools in the system.

## EXAMPLES

### Example 1: Retrieve all storage pools
```
PS C:\> Get-WssSpacesPool
```

This command retrieves all storage pools in the system.

## PARAMETERS

### -ID
Specifies the ID of a storage pool to retrieve.
If you do not specify this parameter, the cmdlet returns a list of all storage pools.
Each storage pool object includes a unique ID.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS



