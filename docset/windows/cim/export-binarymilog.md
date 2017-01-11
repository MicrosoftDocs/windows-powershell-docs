---
author: brianlic-msft
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
title: Export-BinaryMiLog
ms.assetid: 0812F28F-D7B4-4325-A84E-2F274CD4D3E1
---

# Export-BinaryMiLog

## SYNOPSIS
Creates a binary encoded representation of an object or objects and stores it in a file.

## SYNTAX

```
Export-BinaryMiLog [-InputObject <CimInstance>] [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Export-BinaryMILog** cmdlet creates a binary-based representation of an object or objects and stores it in a file.
You can then use the Import-BinaryMiLog cmdlet to re-create the saved object based on the contents of that file.

This cmdlet is similar to Import-Clixml, except that **Export-BinaryMILog** stores the resulting object in a binary encoded file.

## EXAMPLES

### Example 1: Create a binary representation of CimInstances
```
PS C:\> Get-CimInstance Win32_Process | Export-BinaryMiLog -Path "Processes.bmil"
```

This command exports CimInstances to a binary MI log file specified by the *Path* parameter.
See the example for Import-BinaryMiLog to see how to recreate the CimInstances by importing this file.

## PARAMETERS

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path
Specifies the path of the file in which to store the binary representation of the object.

The *Path* parameter supports wild cards and relative paths.
This cmdlet generates an error if the path resolves to more than one file.

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

[Get-CimInstance](./Get-CimInstance.md)

[Import-BinaryMiLog](./Import-BinaryMiLog.md)

