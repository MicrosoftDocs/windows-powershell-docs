---
author: Kateyanne
description: 
external help file: WssCmdlets.dll-Help.xml
manager: jasgro
Module Name: WSSCmdlets
ms.author: v-kaunu
ms.date: 12/05/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssdrive?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssDrive
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

