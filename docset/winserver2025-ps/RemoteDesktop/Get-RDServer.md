---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/get-rdserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RDServer
---

# Get-RDServer

## SYNOPSIS
Gets RDS servers in a Remote Desktop deployment.

## SYNTAX

```
Get-RDServer [[-ConnectionBroker] <String>] [[-Role] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDServer** cmdlet gets the Remote Desktop Services (RDS) servers in a Remote Desktop deployment.
You can get servers by role, or all servers in a deployment.

## EXAMPLES

### Example 1: Get all servers
```
PS C:\> Get-RDserver
```

This command gets all servers and the server roles installed in the Remote Desktop deployment on the local computer.

### Example 2: Get servers that have a specified role
```
PS C:\> Get-RDserver -Role "RDS-VIRTUALIZATION"
```

This command gets the servers that have the RD Virtualization Host server role for the local computer.
The **Role** parameter has the value RDS-VIRTUALIZATION.

### Example 3: Get all servers for an RD Connection Broker
```
PS C:\> Get-RDServer -ConnectionBroker "RDCB.Contoso.com"
```

This command gets the servers and the server roles installed in the Remote Desktop deployment for the RD Connection Broker, named RDCB.Contoso.com.

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

### -Role
Specifies an array of names of RDS service roles.
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
Type: String[]
Parameter Sets: (All)
Aliases:
Accepted values: RDS-VIRTUALIZATION, RDS-RD-SERVER, RDS-CONNECTION-BROKER, RDS-WEB-ACCESS, RDS-GATEWAY, RDS-LICENSING

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object
Server.
FQDN of an RD Connection Broker.
Roles.
Names of RDS role services.

## NOTES

## RELATED LINKS

[Add-RDServer](./Add-RDServer.md)

[Remove-RDServer](./Remove-RDServer.md)

