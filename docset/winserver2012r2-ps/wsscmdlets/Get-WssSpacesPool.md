---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssspacespool?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssSpacesPool
---

# Get-WssSpacesPool

## SYNOPSIS
Retrieves a storage pool, or all storage pools in the system.

## SYNTAX

```
Get-WssSpacesPool [-ID <String>] [<CommonParameters>]
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.WindowsServerSolutions.Storage.SpacesPool
This cmdlet generates the storage pool in the system.

## NOTES

## RELATED LINKS

