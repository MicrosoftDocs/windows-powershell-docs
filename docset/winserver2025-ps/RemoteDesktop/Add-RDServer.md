---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/add-rdserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-RDServer
---

# Add-RDServer

## SYNOPSIS
Adds an RDS server to a Remote Desktop deployment.

## SYNTAX

```
Add-RDServer [-Server] <String> [-Role] <String> [[-ConnectionBroker] <String>]
 [[-GatewayExternalFqdn] <String>] [-CreateVirtualSwitch] [<CommonParameters>]
```

## DESCRIPTION
The **Add-RDServer** cmdlet adds a Remote Desktop Services (RDS) server to a Remote Desktop deployment.
Specify a server to add by using a fully qualified domain name (FQDN) and role service name.
If you add a Remote Desktop Gateway (RD Gateway) role, specify the FQDN for the external gateway.
You can use this cmdlet to create a virtual switch.

## EXAMPLES

### Example 1: Add an RD Session Host server
```
PS C:\> Add-RDServer -Server "SessionHost.Contoso.com" -Role "RDS-RD-SERVER" -ConnectionBroker "RDCB.Contoso.com"
```

This command adds a server named SessionHost.Contoso.com as an RD Session Host server to a deployment that has an RD Connection Broker server named RDCB.Contoso.com.
The RDS-RD-SERVER role indicates an RD Session Host server.

### Example 2: Add an RD Virtualization Host server and create a virtual switch
```
PS C:\>Add-RDServer -Server "VirtualizationHost.Contoso.com" -Role "RDS-VIRTUALIZATION" -ConnectionBroker "RDCB.Contoso.com" -CreateVirtualSwitch
```

This command adds a server named VirtualizationHost.Contoso.com as an RD Virtualization Host server to a deployment that has an RD Connection Broker server named RDCB.Contoso.com.
The command creates a virtual switch.

### Example 3: Add an RD Gateway server
```
PS C:\>Add-RDServer -Server "Gateway.Contoso.com" -Role "RDS-GATEWAY" -ConnectionBroker "RDCB.Contoso.com" -GatewayExternalFqdn "ExternalFQDN.NorthWindTraders.com"
```

This command adds a server named Gateway.Contoso.com as an external gateway to a deployment that has an RD Connection Broker server named RDCB.Contoso.com.
The external FQDN of the gateway is ExternalFQDN.NorthWindTraders.com.

### Example 4: Add an RD Connection Broker server
```
PS C:\>Add-RDServer -Server "RDCB02Contoso.com" -Role "RDS-CONNECTION-BROKER" -ConnectionBroker "RDCB.Contoso.com"
```

This command adds a server named RDCB02Contoso.com as an RD Connection Broker server to a deployment that has an RD Connection Broker server named RDCB.Contoso.com.

## PARAMETERS

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a Remote Desktop deployment.
If you do not specify a value, the cmdlet uses the FQDN of the local computer.

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

### -CreateVirtualSwitch
Indicates that the cmdlet creates a virtual switch.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GatewayExternalFqdn
Specifies the external FQDN of the RD Gateway server for this Remote Desktop deployment.
Use this parameter when you are adding the RD Gateway role service.
The **Role** parameter value is RDS-GATEWAY.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
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
RD Gateway.
- RDS-LICENSING.
Remote Desktop Licensing (RD Licensing).

If you select a value of RDS-GATEWAY for this parameter, supply a value for the **GatewayExternalFqdn** parameter.

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
Specifies the FQDN of the server to add to the Remote Desktop deployment.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

This cmdlet accepts no input.

## OUTPUTS

### Null

## NOTES

## RELATED LINKS

[Get-RDServer](./Get-RDServer.md)

[Remove-RDServer](./Remove-RDServer.md)
