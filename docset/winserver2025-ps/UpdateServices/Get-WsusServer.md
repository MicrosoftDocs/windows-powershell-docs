---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.UpdateServices.Commands.dll-Help.xml
Module Name: UpdateServices
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/updateservices/get-wsusserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WsusServer
---

# Get-WsusServer

## SYNOPSIS

Gets the WSUS update server object.

## SYNTAX

### DefaultServer (Default)

```powershell
Get-WsusServer [<CommonParameters>]
```

### ServerSpecified

```powershell
Get-WsusServer [-Name] <String> [-UseSsl] -PortNumber <Int32> [<CommonParameters>]
```

## DESCRIPTION

The **Get-WsusServer** cmdlet gets the Windows Server Update Services (WSUS) update server object. This cmdlet requires the server name, port number and a flag that specifies if the server uses Secure Sockets Layer (SSL) as parameters.

Given a server name, port number, and flag specifying whether to use SSL, returns an **IUpdateServer** object.

## EXAMPLES

### Example 1: Get the local server

```text
PS C:\> Get-WsusServer
Name : contoso
```

This command gets the **IUpdateServer** object for the local computer.

### Example 2: Get a remote server

```text
PS C:\> Get-WsusServer -Name "contoso" -PortNumber 8530
Name : contoso
```

This command gets the **IUpdateServer** object for a remote computer.

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.UpdateServices.Administration.IUpdateServer

## NOTES

## RELATED LINKS
