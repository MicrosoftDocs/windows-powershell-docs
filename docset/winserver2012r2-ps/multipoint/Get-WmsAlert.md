---
external help file: WmsCmdlets.dll-Help.xml
Module Name: WmsCmdlets
online version: 
schema: 2.0.0
title: Get-WmsAlert
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/06/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: D5646741-42DF-4681-8CBD-0D3FF6A80986
ms.reviewer:
ms.author: v-kaunu
---

# Get-WmsAlert

## SYNOPSIS
Returns alert information.

## SYNTAX

```
Get-WmsAlert [-SerializeString] [-TimeoutInSecond <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The Get-WmsAlert cmdlet returns alert information from the Windows MultiPoint Server Core Service.

## EXAMPLES

### Example
```
PS C:\> Get-WmsAlert
TimeStampInUtc : 12/7/2010 12:17:15 AM


AlertType      : HubMissingRequiredDevice


AlertSeverity  : Warning


ComputerName   : TEST


StationId      : 1
```

This cmdlet returns alert information from the Windows MultiPoint Server Core Service.
In the following example, a station is missing a keyboard.

### 1:
```
PS C:\>
```

## PARAMETERS

### -SerializeString
Returns data in XML format.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -TimeoutInSecond
The timeout value in seconds before the operation is aborted.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

###  
Returns WmsAlert collection as PSObject collection.

## NOTES

## RELATED LINKS

