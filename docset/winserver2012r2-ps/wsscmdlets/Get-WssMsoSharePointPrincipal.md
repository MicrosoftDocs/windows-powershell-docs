---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssMsoSharePointPrincipal
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: AFAA2829-1512-447B-9E9F-EF23657295CC
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssMsoSharePointPrincipal

## SYNOPSIS
Gets all sp_2013_2 principal objects, including users and groups.

## SYNTAX

```
Get-WssMsoSharePointPrincipal [[-UserName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssMsoSharePointPrincipal** cmdlet gets all sp_2013_1 principal objects, including sp_2013_2 users and groups.

## EXAMPLES

### Example 1: Get principal objects
```
PS C:\> $Principals = Get-WssMsoSharePointPrincipal
```

This command gets the sp_2013_2 principal objects.

### 1:
```
PS C:\>
```

## PARAMETERS

### -UserName
Specifies a name for a user account.
The cmdlet gets all sp_2013_2 principal objects for the user name that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### SharepointPrincipal[]

## NOTES

## RELATED LINKS

