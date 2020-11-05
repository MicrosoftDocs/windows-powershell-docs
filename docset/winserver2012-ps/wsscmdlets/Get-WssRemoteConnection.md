---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: FD98B9EC-0249-45D9-B2AD-B3CD70A8639E
manager: dansimp
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



