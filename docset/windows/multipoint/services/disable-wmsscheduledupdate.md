---
author: brianlic
description: 
external help file: MultiPoint.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Disable-WmsScheduledUpdate
ms.assetid: DA709A52-8A83-4845-ACAC-99A0E288970C
---

# Disable-WmsScheduledUpdate

## SYNOPSIS
Disables scheduled updates while disk protection is enabled and in discard mode.

## SYNTAX

```
Disable-WmsScheduledUpdate [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-WmsScheduledUpdate** cmdlet disables scheduled updates while disk protection is enabled and in discard mode.

## EXAMPLES

### Example 1: Disable scheduled updates on the local computer
```
PS C:\>Disable-WmsScheduledUpdate
```

This command disables scheduled updates on the local computer.

### Example 2: Disable schedule updates for a specified computer
```
PS C:\>Disable-WmsScheduledUpdate -Server "sample.microsoft.com"
```

This command disables scheduled updates on the computer sample.microsoft.com

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-WmsScheduledUpdate](./Enable-WmsScheduledUpdate.md)

[Get-WmsScheduledUpdate](./Get-WmsScheduledUpdate.md)

[Set-WmsScheduledUpdate](./Set-WmsScheduledUpdate.md)

