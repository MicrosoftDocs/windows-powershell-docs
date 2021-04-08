---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssremoteconnection?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WssRemoteConnection

## SYNOPSIS
Retrieves a listing of remote connections from Remote Web Access clients, VPN clients, or Web API applications.

## SYNTAX

```
Get-WssRemoteConnection [-From <DateTime>]
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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS



