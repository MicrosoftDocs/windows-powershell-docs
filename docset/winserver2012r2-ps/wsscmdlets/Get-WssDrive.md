---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssDrive
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 485624A7-B40A-47DF-AF78-B12EC35B90DA
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssDrive

## SYNOPSIS
Gets an object that represents a drive.

## SYNTAX

```
Get-WssDrive [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssDrive** cmdlet gets an object that represents a drive.
Specify a GUID for a specific drive.
If you do not specify a GUID, the cmdlet gets **Drive** objects for all the drives for the current server.

## EXAMPLES

### Example 1: Get all drives
```
PS C:\> Get-WssDrive
```

This command gets **Drive** objects for all the drives for the current server.

## PARAMETERS

### -ID
Specifies the GUID for a drive.

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

### Microsoft.WindowsServerSolutions.Storage.Drive
This cmdlet generates the server **Drive** object.

## NOTES

## RELATED LINKS

[Set-WssDrive](./Set-WssDrive.md)

[Test-WssDrive](./Test-WssDrive.md)

