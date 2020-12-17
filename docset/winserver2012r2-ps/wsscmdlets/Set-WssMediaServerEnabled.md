---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Set-WssMediaServerEnabled
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 7B50DA56-FCFF-458D-9509-27001D232E00
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-WssMediaServerEnabled

## SYNOPSIS
Enables or disables media streaming on a server.

## SYNTAX

```
Set-WssMediaServerEnabled [-Enable] <Boolean> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssMediaServerEnabled** cmdlet enables or disables media streaming for the current server.
You can use the Get-WssMediaServerEnabled cmdlet to see the status of media streaming.

## EXAMPLES

### Example 1: Disable media streaming
```
PS C:\> Set-WssMediaServerEnabled -Enable $False
```

This command disables media streaming for the current server.

## PARAMETERS

### -Enable
Indicates whether the cmdlet enables or disables media streaming.
Use a value of $True to enable media streaming, or a value of $False to disable it.

```yaml
Type: Boolean
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

## NOTES

## RELATED LINKS

[Get-WssMediaServerEnabled](./Get-WssMediaServerEnabled.md)

