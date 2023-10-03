---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/get-wssbpascanresult?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssBpaScanResult
---

# Get-WssBpaScanResult

## SYNOPSIS
Gets the most recent BPA scan result.

## SYNTAX

```
Get-WssBpaScanResult [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssBpaScanResult** cmdlet gets the most recent Best Practices Analyzer (BPA) scan result.
The BPA compares the server configuration with guidelines for the ideal way, under normal circumstances, to configure a server.

## EXAMPLES

### Example 1: Get a BPA scan result
```
PS C:\> Get-WssBpaScanResult
```

This command gets the most recent BPA scan result.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.BPA.WssBpaIssue
This cmdlet returns BPA issues.

## NOTES

## RELATED LINKS

[Invoke-WssBpaScan](./Invoke-WssBpaScan.md)

