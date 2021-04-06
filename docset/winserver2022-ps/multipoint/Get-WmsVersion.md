---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-WmsVersion
ms.reviewer:
ms.assetid: 7D06B35A-0D4F-4226-8B09-5225D92CFEA7
---

# Get-WmsVersion

## SYNOPSIS
Gets the server version, the Connector version, and the SKU.

## SYNTAX

```
Get-WmsVersion [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WmsVersion** cmdlet gets the MultiPoint Server version, the MultiPoint Connector version, and the MultiPoint SKU.

## EXAMPLES

### Example 1: Get the MultiPoint version
```
PS C:\> Get-WmsVersion
ServerVersion                 ClientVersion                         SKU     ProtocolVersion
-------------                 -------------                         ---     ---------------
10.0.10586.0                  10.0.10586.0                          77      1
```

This command gets the version information for the current computer.

## PARAMETERS

### -Server
Specifies the fully qualified host name of the MultiPoint Server that is the target of the command.
The default is localhost.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

###  
Returns the **WmsVersion** collection as **PSObject** collection.

## NOTES

## RELATED LINKS

