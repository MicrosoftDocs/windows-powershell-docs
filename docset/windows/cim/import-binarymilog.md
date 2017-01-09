---
author: brianlic
description: 
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Import-BinaryMiLog
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
The **Import-BinaryMILog** cmdlet imports a binary MI log file that was created by using the Export-BinaryMiLog command that contains data representing objects and then creates the objects in Windows PowerShell.

## EXAMPLES

### Example 1: Import a binary MI log file
```
PS C:\> $Processes = Import-BinaryMiLog -Path "Processes.bmil"
```

This example recreates the CimInstances from the data file created in the example for Export-BinaryMiLog and saves it to a PowerShell variable.

## PARAMETERS

### -Path
Specified the log file to import.
The *Path* parameter supports wildcard characters and relative paths.
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

[Export-BinaryMiLog](./Export-BinaryMiLog.md)

