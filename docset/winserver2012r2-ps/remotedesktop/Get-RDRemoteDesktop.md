---
external help file: 
Module Name: RemoteDesktop
online version: 
schema: 2.0.0
title: Get-RDRemoteDesktop
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 37504AB6-22BD-495A-81BC-032541BD594B
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-RDRemoteDesktop

## SYNOPSIS
Gets published Remote Desktop connections.

## SYNTAX

```
Get-RDRemoteDesktop [[-ConnectionBroker] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDRemoteDesktop** cmdlet gets published Remote Desktop connections.

When you publish a Remote Desktop connection, the Remote Desktop Web Access (RD Web Access) server displays the Remote Desktop connection for the collection defined by the **CollectionName** parameter.
RemoteApp and Desktop Connections that the user subscribes to also display published Remote Desktop connections.

## EXAMPLES

### Example 1: Get the published virtual desktops for all collections
```
PS C:\> Get-RDRemoteDesktop -ConnectionBroker "RDCB.Contoso.com"
```

This command gets the published virtual desktops for collections on the RD Connection Broker named RDCB.Contoso.com.

## PARAMETERS

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a Remote Desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.RemoteDesktopServices.Management.RDPublishedRemoteDesktop

## NOTES

## RELATED LINKS

[Set-RDRemoteDesktop](./Set-RDRemoteDesktop.md)

