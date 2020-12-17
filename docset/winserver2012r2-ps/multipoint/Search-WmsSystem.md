---
external help file: WmsCmdlets.dll-Help.xml
Module Name: WmsCmdlets
online version: 
schema: 2.0.0
title: Search-WmsSystem
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/06/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 8954DC2F-5DEF-4B55-A9E7-9BBCD01D5435
ms.reviewer:
ms.author: v-kaunu
---

# Search-WmsSystem

## SYNOPSIS
Returns a list of other MultiPoint servers or a personal computer running MultiPoint connectors in the same network.

## SYNTAX

```
Search-WmsSystem [-SerializeString] [-TimeoutInSecond <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The Search-WmsSystem cmdlet returns a list of other MultiPoint servers or a personal computer running MultiPoint connectors in the same network.
The operation takes 10 seconds to complete.

## EXAMPLES

### Example
```
PS C:\> Search-WmsSystem -ManagedSystemsType MultiPointServers
Test2

Test3
```

The cmdlet returns peer Windows MultiPoint servers in the same sub-net. 
The query takes 10 seconds to complete and uses WSDAPI protocol to discover peer MultiPoint servers in the network.

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
Specifies a Remote Desktop Session (RDS) using SessionID.

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
Returns string collection as PSObject collection.

## NOTES

## RELATED LINKS

