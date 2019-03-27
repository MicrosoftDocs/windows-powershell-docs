---
external help file: Microsoft.UpdateServices.Commands.dll-Help.xml
Module Name: UpdateServices
online version: 
schema: 2.0.0
title: Get-WsusServer
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 78345E36-259A-4D81-BEF1-9CB69C043427
ms.author: kenwith
ms.reviewer: brianlic
---

# Get-WsusServer

## SYNOPSIS
Gets the Windows Server Update Services (WSUS) update server object.

## SYNTAX

### DefaultServer (Default)
```
Get-WsusServer [<CommonParameters>]
```

### ServerSpecified
```
Get-WsusServer [-Name] <String> [-UseSsl] -PortNumber <Int32> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WsusServer** cmdlet gets the Windows Server Update Services (WSUS) update server object.
This cmdlet requires the server name, port number and a flag that specifies if the server uses Secure Sockets Layer (SSL) as parameters.

Given a server name, port number, and flag specifying whether to use SSL, returns an IUpdateServer object.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-WsusServer
Name : contoso
```

This example gets the IUpdateServer object for the local machine.

### EXAMPLE 2
```
PS C:\> Get-WsusServer -Name contoso -PortNumber 8530
Name : contoso
```

This example gets the IUpdateServer object for a remote machine.

## PARAMETERS

### -Name
Specifies the name of a WSUS server.

```yaml
Type: String
Parameter Sets: ServerSpecified
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PortNumber
Specifies the port number to use to communicate with the upstream WSUS server.

```yaml
Type: Int32
Parameter Sets: ServerSpecified
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSsl
Specifies that the WSUS server should use Secure Sockets Layer (SSL) via HTTPS to communicate with an upstream server.

```yaml
Type: SwitchParameter
Parameter Sets: ServerSpecified
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.UpdateServices.Commands.IUpdateServer
IUpdateServer

## NOTES

## RELATED LINKS

