---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Set-WssServerConnectionOption
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 3C56CEC7-14C5-46B9-A1F9-7DD31D893693
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-WssServerConnectionOption

## SYNOPSIS
Modifies the server connection option.

## SYNTAX

```
Set-WssServerConnectionOption -Option <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssServerConnectionOption** cmdlet modifies the server connection option in sbs_sbs8_2.
WSS supports the use of a terminal session directly to the server (RemoteDesktop) or the use of the dashboard as a remote application (RemoteApp).

## EXAMPLES

### Example 1: Set the connection option
```
PS C:\> Set-WssServerConnectionOption -Option RemoteDesktop
```

This command sets the connection option for the WSS server to RemoteDesktop.

## PARAMETERS

### -Option
Specifies the server connection option.
Valid values for this parameter are: RemoteDesktop or RemoteApp.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
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

[Get-WssServerConnectionOption](./Get-WssServerConnectionOption.md)

