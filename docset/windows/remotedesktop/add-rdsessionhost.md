---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: 
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Add-RDSessionHost
ms.reviewer:
ms.assetid: 2E434A50-1560-4205-81A4-516FD3B3E686
---

# Add-RDSessionHost

## SYNOPSIS
Adds one or more RD Session Host servers to a session collection.

## SYNTAX

```
Add-RDSessionHost [-CollectionName] <String> -SessionHost <String[]> [-ConnectionBroker <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-RDSessionHost** cmdlet adds one or more Remote Desktop Session Host (RD Session Host) servers to a session collection.
RD Session Host is a Remote Desktop Services role service that enables users to share Windows-based programs or the full Windows desktop.
Users can connect to an RD Session Host server to run programs, save files, and use network resources on that server.

## EXAMPLES

### Example 1: Add an RD Session Host server to a session collection on an RD Connection Broker server
```
PS C:\> Add-RDSessionHost -SessionHost "sessionhost.contoso.com" -ConnectionBroker "rdcb.contoso.com"
```

This command adds an RD Session Host server named sessionhost.contoso.com to a session collection.
Remote users connect to the RD Connection Broker server named rdcb.contoso.com to obtain views of available RemoteApp programs, session-based desktops, and virtual desktops.

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
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for this Remote Desktop deployment.
Remote users connect to this server to obtain views of available firstref_server_7 RemoteApp programs, session-based desktops, and virtual desktops.
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

### -SessionHost
Specifies an array that contains the name of one or more servers that run the RD Session Host role service.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null

## NOTES

## RELATED LINKS

[Get-RDSessionHost](./Get-RDSessionHost.md)

[Remove-RDSessionHost](./Remove-RDSessionHost.md)

[Set-RDSessionHost](./Set-RDSessionHost.md)

