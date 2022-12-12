---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/get-wssbranchcachestatus?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssBranchCacheStatus
---

# Get-WssBranchCacheStatus

## SYNOPSIS
Gets the current BranchCache status.

## SYNTAX

```
Get-WssBranchCacheStatus [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssBranchCacheStatus** cmdlet gets the current BranchCache service status on the target computer, either enabled or disabled.
BranchCache copies content from on-premise content servers or hosted cloud content servers and caches the content at branch office locations.

## EXAMPLES

### Example 1: Get BranchCache status
```
PS C:\> Get-WssBranchCacheStatus
```

This command gets the status of BranchCache on the server where you run the cmdlet.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.BranchCache.BranchCacheStatus

## NOTES

## RELATED LINKS

