---
external help file: 
Module Name: RemoteDesktop
online version: 
schema: 2.0.0
title: Get-RDSessionHost
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 7F8BD30F-62B9-49C0-984A-59D735A181FC
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-RDSessionHost

## SYNOPSIS
Gets a list of RD Session Host servers in a session collection.

## SYNTAX

```
Get-RDSessionHost [-CollectionName] <String> [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDSessionHost** cmdlet gets a list of Remote Desktop Session Host (RD Session Host) servers in a session collection.
RD Session Host is a Remote Desktop Services role service that lets users share Windows-based programs or the full Windows desktop.
Users can connect to an RD Session Host server to run programs, save files, and use network resources on that server.

## EXAMPLES

### Example 1: Retrieve a list of RD  Session Host servers in a session collection
```
PS C:\> Get-RDSessionHost -CollectionName "Session Collection" -ConnectionBroker rdcb.contoso.com
```

This command retrieves a list of the RD Session Host servers in the session collection named Session Collection, which is associated with the RD Connection Broker server named rdcb.contoso.com.

## PARAMETERS

### -CollectionName
Specifies the name of the RD Session Host collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD  Connection Broker) server for this Remote Desktop deployment.
If this parameter does not appear, the default value is the fully qualified domain name (FQDN) of the local host.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.RemoteDesktopServices.Management.RDServer

## NOTES

## RELATED LINKS

[Add-RDSessionHost](./Add-RDSessionHost.md)

[Remove-RDSessionHost](./Remove-RDSessionHost.md)

[Set-RDSessionHost](./Set-RDSessionHost.md)

