---
external help file: WmsCmdlets.dll-Help.xml
Module Name: WmsCmdlets
online version: 
schema: 2.0.0
title: Get-WmsUser
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/06/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: EA8744D5-B53A-4C3E-AE80-5D4A9252E6FB
ms.reviewer:
ms.author: v-kaunu
---

# Get-WmsUser

## SYNOPSIS
Returns all local user account information.

## SYNTAX

```
Get-WmsUser [-SerializeString] [-TimeoutInSecond <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The Get-WmsUser cmdlet returns all local user account information.

## EXAMPLES

### Example
```
PS C:\> Get-WmsUser
Name         : Administrator


Password     : 


FullName     : 


Description  : Built-in account for administering the computer/domain


UserType     : Administrator


ComputerName : Test1



Name         : Guest


Password     : 


FullName     : 


Description  : Built-in account for guest access to the computer/domain


UserType     : Standard


ComputerName : Test1
```

Returns all local user account information.

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
Returns WmsUser collection as PSObject collection.

## NOTES

## RELATED LINKS

