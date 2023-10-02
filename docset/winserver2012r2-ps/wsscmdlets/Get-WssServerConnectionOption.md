---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/get-wssserverconnectionoption?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssServerConnectionOption
---

# Get-WssServerConnectionOption

## SYNOPSIS
Retrieves the server connection option.

## SYNTAX

```
Get-WssServerConnectionOption [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssServerConnectionOption** cmdlet retrieves the server connection option in sbs_sbs8_2.
WSS supports the use of a terminal session directly to the server (RemoteDesktop) or the use of the dashboard as a remote application (RemoteApp).

## EXAMPLES

### Example 1: Get the server connection option
```
PS C:\> Get-WssServerConnectionOption
```

This command gets the server connection option.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String
This cmdlet generates a string object representing the server connection option, either RemoteDesktop or RemoteApp (Dashboard).

## NOTES

## RELATED LINKS

[Set-WssServerConnectionOption](./Set-WssServerConnectionOption.md)

