---
external help file: 
Module Name: RemoteDesktop
online version: 
schema: 2.0.0
title: Get-RDVirtualDesktopConcurrency
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 1F4FDD12-F775-4A69-855E-0F86EF4BF9D0
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-RDVirtualDesktopConcurrency

## SYNOPSIS
Gets the number of virtual desktops that RDS can create in parallel.

## SYNTAX

```
Get-RDVirtualDesktopConcurrency [[-HostServer] <String[]>] [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDVirtualDesktopConcurrency** cmdlet gets the number of virtual desktops that Remote Desktop Services (RDS) can create in parallel on one or more Remote Desktop Virtualization Host (RD Virtualization Host) servers.

## EXAMPLES

### Example 1: Get the number of virtual desktops that RDS can create in parallel on host servers
```
PS C:\> Get-RDVirtualDesktopConcurrency -ConnectionBroker "rdcb.contoso.com" -HostServer @("rdvh-1.contoso.com","rdvh-2.contoso.com")
```

This command gets the number of virtual desktops that Remote Desktop Services (RDS) can create in parallel on the host servers named "rdvh-1.contoso.com" and "rdvh-2.contoso.com".

### Example 2: Get the number of virtual desktops that RDS can create in parallel on all host servers
```
PS C:\> Get-RDVirtualDesktopConcurrency -ConnectionBroker "rdcb.contoso.com"
```

This command gets the number of virtual desktops that Remote Desktop Services (RDS) can create in parallel on all the host servers associated with the RD Connection Broker server named "rdcb.contoso.com".

## PARAMETERS

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a remote desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

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

### -HostServer
Specifies an array of names of the servers that host the session.
For session collections the host server has the name of the Remote Desktop Session Host (RD Session Host) server.
For virtual desktop collections the host server has the name of the Remote Desktop Virtualization Host (RD Virtualization Host) server.

```yaml
Type: String[]
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

### System.Object

## NOTES

## RELATED LINKS

[Set-RDVirtualDesktopConcurrency](./Set-RDVirtualDesktopConcurrency.md)

