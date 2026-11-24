---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/remove-rdserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-RDServer
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
Forces the command to run without asking for user confirmation.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null

## NOTES

## RELATED LINKS

[Add-RDServer](./Add-RDServer.md)

[Get-RDServer](./Get-RDServer.md)

