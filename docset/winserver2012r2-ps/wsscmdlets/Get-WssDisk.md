---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssDisk
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 55016D8F-D352-49B7-83E4-6F855D95D6A6
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssDisk

## SYNOPSIS
Gets an object that represents a disk.

## SYNTAX

```
Get-WssDisk [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssDisk** cmdlet gets an object that represents a disk.
Specify a GUID for a specific disk.
If you do not specify a GUID, the cmdlet gets Disk objects for all the drives for the current server.
You can use the Initialize-WssDisk cmdlet to initialize a disk for sbs_sbs8_1 storage.

## EXAMPLES

### Example 1: Get a Disk object
```
PS C:\> Get-WssDisk -ID "26a21bda-a627-11d7-9931-806e6f6e6963"
```

This command gets the Disk object that has the ID 26a21bda-a627-11d7-9931-806e6f6e6963.

## PARAMETERS

### -ID
Specifies the GUID for a disk.

```yaml
Type: Guid
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

## OUTPUTS

### Microsoft.WindowsServerSolutions.Storage.Disk
This cmdlet generates the server **Disk** object.

## NOTES

## RELATED LINKS

[Initialize-WssDisk](./Initialize-WssDisk.md)

