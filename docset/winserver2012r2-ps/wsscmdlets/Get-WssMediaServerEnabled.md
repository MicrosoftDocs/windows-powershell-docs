---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssmediaserverenabled?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssMediaServerEnabled
---

# Get-WssMediaServerEnabled

## SYNOPSIS
Gets the status of media streaming for a server.

## SYNTAX

```
Get-WssMediaServerEnabled [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssMediaServerEnabled** cmdlet gets the status of media streaming for the current server.
You can use the Set-WssMediaServerEnabled cmdlet to enable or disable media streaming.

## EXAMPLES

### Example 1: Get media streaming status
```
PS C:\> Get-WssMediaServerEnabled
```

This command gets the media streaming status for the current server.
Media streaming is either enabled or disabled.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Boolean
This cmdlet generates a Boolean value that indicates whether or not media streaming is enabled on the server.

## NOTES

## RELATED LINKS

[Set-WssMediaServerEnabled](./Set-WssMediaServerEnabled.md)

