---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssDriveInUse
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 9C4607C0-4DFD-408D-AA76-E40F914CC7B5
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssDriveInUse

## SYNOPSIS
Checks whether a drive is in use.

## SYNTAX

```
Get-WssDriveInUse [-Drive] <Drive> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssDriveInUse** cmdlet checks whether a drive is in use.
To obtain a **Drive** object to check, use the Get-WssDrive cmdlet.

## EXAMPLES

### Example 1: Check whether a drive is in use
```
PS C:\>$Drive = Get-WssDrive -ID b6b093a2-1860-4172-a4a5-07ce2aebfa13
PS C:\> Get-WssDriveInUse -Drive $Drive
```

This example checks whether a specified drive is in use.
The first command uses the Get-WssDrive cmdlet to get a **Drive** object that has the specified GUID, and stores it in the **$Drive** variable.

The second command checks whether the **Drive** object stored in the **$Drive** variable is in use.

## PARAMETERS

### -Drive
Specifies a **Drive** object.
To obtain a **Drive** object, use the Get-WssDrive cmdlet.

```yaml
Type: Drive
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.Storage.DriveInUseRequest
This cmdlet generates a drive in use indicator.

## NOTES

## RELATED LINKS

[Get-WssDrive](./Get-WssDrive.md)

