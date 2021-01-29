---
external help file: 
Module Name: RemoteDesktop
online version: 
schema: 2.0.0
title: Remove-RDServer
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: F36CC27A-AE6B-4017-A1FC-6253B607566E
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-RDServer

## SYNOPSIS
Removes a server from a Remote Desktop deployment.

## SYNTAX

```
Remove-RDServer [-Server] <String> [-Role] <String> [[-ConnectionBroker] <String>] [-Force]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-RDServer** cmdlet removes a specified Remote Desktop Services (RDS) server from a Remote Desktop deployment.
This cmdlet does not uninstall a server or server role.

## EXAMPLES

### Example 1: Remove an RD Virtualization Host
```
PS C:\> Remove-RDServer -Server "RDVH.Contoso.com" -Role "RDS-VIRTUALIZATION" -ConnectionBroker "RDCB.Contoso.com"
```

This command removes an RD Virtualization Host server named RDVH.Contoso.com from the deployment that has an RD Connection Broker server named RDCB.Contoso.com.

## PARAMETERS

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a Remote Desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Performs the action without a confirmation message.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Role
Specifies an RDS role service name.
The acceptable values for this parameter are:

- RDS-VIRTUALIZATION.
Remote Desktop Virtualization Host (RD Virtualization Host).
- RDS-RD-SERVER.
Remote Desktop Session Host (RD Session Host).
- RDS-CONNECTION-BROKER.
RD Connection Broker.
- RDS-WEB-ACCESS.
Remote Desktop Web Access (RD Web Access).
- RDS-GATEWAY.
Remote Desktop Gateway (RD Gateway).
- RDS-LICENSING.
Remote Desktop Licensing (RD Licensing).

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: RDS-CONNECTION-BROKER, RDS-VIRTUALIZATION, RDS-RD-SERVER, RDS-WEB-ACCESS, RDS-GATEWAY, RDS-LICENSING

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Specifies the FQDN of the server to be removed from the Remote Desktop deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null

## NOTES

## RELATED LINKS

[Add-RDServer](./Add-RDServer.md)

[Get-RDServer](./Get-RDServer.md)

