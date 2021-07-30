---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/invoke-wssbpascan?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WssBpaScan
---

# Invoke-WssBpaScan

## SYNOPSIS
Starts a BPA scan.

## SYNTAX

```
Invoke-WssBpaScan [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-WssBpaScan** cmdlet starts a Best Practices Analyzer (BPA) scan that raises BPA error or warning alerts.
The BPA compares the server configuration with guidelines for the ideal way, under normal circumstances, to configure a server.

## EXAMPLES

### Example 1: Start a BPA scan
```
PS C:\> Invoke-WssBpaScan
```

This command starts a BPA scan.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssBpaScanResult](./Get-WssBpaScanResult.md)

