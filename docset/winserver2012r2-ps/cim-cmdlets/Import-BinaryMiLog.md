---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Module Name: CimCmdlets
online version: 
schema: 2.0.0
title: Import-BinaryMiLog
description: 
keywords: powershell, cmdlet
author: brianlic
manager: alanth
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 30A16D83-3209-4F85-A530-4DF388CEEC44
---

# Import-BinaryMiLog

## SYNOPSIS
Imports a binary MI log file and creates the corresponding objects in Windows PowerShell.

## SYNTAX

```
Import-BinaryMiLog [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Import-BinaryMILog** cmdlet imports a binary MI log file that was created by using the Export-BinaryMILog command that contains data representing objects and then creates the objects in Windows PowerShell.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\> $processes = Import-BinaryMiLog -Path Processes.bmil
```

Description

-----------

This example recreates the CimInstances from the data file created in the example for Export-BinaryMILog and saves it to a PowerShell variable.

## PARAMETERS

### -Path
Specified the log file to import.

The **Path** parameter supports wild cards, and relative paths. 
The cmdlet generates an error if the path resolves to more than one file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Export-BinaryMILog](./Export-BinaryMiLog.md)

