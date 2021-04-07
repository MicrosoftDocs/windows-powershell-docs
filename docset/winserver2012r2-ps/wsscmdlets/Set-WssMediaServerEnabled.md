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
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wssmediaserverenabled?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WssMediaServerEnabled
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

