---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/set-rddeploymentgatewayconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RDDeploymentGatewayConfiguration
---

# Set-RDDeploymentGatewayConfiguration

## SYNOPSIS
Specifies settings for the RD Gateway server for a Remote Desktop deployment.

## SYNTAX

```
Set-RDDeploymentGatewayConfiguration [-GatewayMode] <GatewayUsage> [[-GatewayExternalFqdn] <String>]
 [[-LogonMethod] <GatewayAuthMode>] [[-UseCachedCredentials] <Boolean>] [[-BypassLocal] <Boolean>]
 [[-ConnectionBroker] <String>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Set-RDDeploymentGatewayConfiguration** cmdlet specifies settings for the Remote Desktop Gateway (RD Gateway) server for a Remote Desktop deployment.
These settings include whether to use the RD Gateway server, user authentication methods, and other connection and authentication options.
The RD Gateway role service enables authorized users to connect to virtual desktops, RemoteApp programs, and session-based desktops on an internal corporate network from any Internet-connected device.

## EXAMPLES

### Example 1: Specify settings to configure RD Gateway access
```
PS C:\> Set-RDDeploymentGatewayConfiguration -GatewayMode Automatic -GatewayExternalFQDN "rdg.contoso.com" -LogonMethod AllowUserToSelectDuringConnection -UseCachedCredentials $True -BypassLocal $True -ConnectionBroker "rdcb.contoso.com"
```

This command sets these options for the RD Gateway server:

- Authorized users automatically detect settings from the RD Gateway server.

- The RD Gateway server has an FQDN of rdcb.contoso.com.

- Remote users authenticate access when they connect, use RD Gateway access credentials to authenticate access to the remote computer, and bypass the RD Gateway server for local connections.

- The cmdlet also specifies rdcb.contoso.com as the RD Connection Broker server.

## PARAMETERS

### -BypassLocal
Indicates whether authorized remote users bypass the RD Gateway server for local connections.
By default, the value of this parameter is $False.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for this Remote Desktop deployment.
If this parameter does not appear, the default value is the fully qualified domain name (FQDN) of the local host.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
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

### -GatewayExternalFqdn
Specifies the external FQDN of the RD Gateway server for this Remote Desktop deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GatewayMode
Specifies a value that indicates whether or not authorized remote users use the RD Gateway server and, if so, whether they detect existing RD Gateway settings automatically or enter settings manually.
The acceptable values for this parameter are:

- DoNotUse: Remote users enter settings manually and do not use the Gateway.
- Custom: Remote users get Gateway settings from other parameters to this cmdlet.
- Automatic: Remote users detect Gateway settings automatically.

```yaml
Type: GatewayUsage
Parameter Sets: (All)
Aliases:
Accepted values: DoNotUse, Custom, Automatic

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LogonMethod
Specifies the method for authenticating user access to the RD Gateway server.
The acceptable values for this parameter are:

- GatewayAuthMode: Users authenticate by using the method that the Gateway specifies (using a smart card reader or a password).

- AllowUserToSelectDuringConnection: The Gateway prompts users to authenticate access when they connect.
They must specify a password or smart card reader as the authentication method.

```yaml
Type: GatewayAuthMode
Parameter Sets: (All)
Aliases:
Accepted values: Password, Smartcard, AllowUserToSelectDuringConnection

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseCachedCredentials
Indicates whether or not remote users can use RD Gateway access credentials to authenticate access to the remote computer.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null
None

## NOTES

## RELATED LINKS

[Get-RDDeploymentGatewayConfiguration](./Get-RDDeploymentGatewayConfiguration.md)

