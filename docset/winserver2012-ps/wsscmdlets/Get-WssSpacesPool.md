---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssspacespool?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
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



