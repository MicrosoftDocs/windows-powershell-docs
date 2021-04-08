---
author: Kateyanne
external help file: WSUS_Cmdlets.xml
manager: dansimp
Module Name: UpdateServices
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/updateservices/get-wsusserver?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WsusServer

## SYNOPSIS
Gets the Windows Server Update Services (WSUS) update server object.

## SYNTAX

```
Get-WsusServer [-Name] <String> [-UseSsl] -PortNumber <Int32>
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
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PortNumber
Specifies the port number to use to communicate with the upstream WSUS server.

```yaml
Type: Int32
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.UpdateServices.Commands.IUpdateServer
IUpdateServer

## NOTES

## RELATED LINKS

