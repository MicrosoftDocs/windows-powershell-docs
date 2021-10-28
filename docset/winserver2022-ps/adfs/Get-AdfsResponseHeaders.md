---
description: Gets the response headers that are included in the outgoing HTTP response sent by AD FS to a web
browser.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: adfs
ms.date: 10/28/2021
online version: https://docs.microsoft.com/powershell/module/adfs/get-adfsresponseheaders?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsResponseHeaders
---

# Get-AdfsResponseHeaders

## SYNOPSIS
Gets the response headers that are included in the outgoing HTTP response sent by AD FS to a web
browser.

## SYNTAX

```
Get-AdfsResponseHeaders [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsResponseHeaders** cmdlet gets the response headers that are included in the outgoing
HTTP response sent by AD FS to a web browser.

The response headers will be sent only if ResponseHeadersEnabled is set to True (default value). You
can change the value using **Set-AdfsResponseHeaders**.

## EXAMPLES

### Example 1: Gets the HTTP response headers sent by AD FS to a web browser.
```powershell
PS> Get-AdfsResponseHeaders
```

Lists the HTTP response headers included in every outgoing HTTP response.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
