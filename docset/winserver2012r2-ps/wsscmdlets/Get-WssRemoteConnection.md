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
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssremoteconnection?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssRemoteConnection
---

# Get-WssRemoteConnection

## SYNOPSIS
Retrieves a listing of remote connections from Remote Web Access clients, VPN clients, or Web API applications.

## SYNTAX

```
Get-WssRemoteConnection [-From <DateTime>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssRemoteConnection** cmdlet retrieves a listing of remote connections to the sbs_sbs8_2 server by Remote Web Access clients, VPN clients, or Web API applications.

## EXAMPLES

### Example 1: Retrieve a listing of remote connections
```
PS C:\> Get-WssRemoteConnection
```

This command retrieves a listing of all current remote connections to the server.

## PARAMETERS

### -From
Specifies a starting time from which to return connections.
If you do not specify this parameter, the cmdlet retrieves all active connections.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: System.DateTime.MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.RemoteConnectionManager.RemoteConnectionInfo
This cmdlet generates information of remote connections to the server from Remote Web Access, VPN, or Web API applications.

## NOTES

## RELATED LINKS

