---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollervirtualswitchconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerVirtualSwitchConfiguration
---

# Get-NetworkControllerVirtualSwitchConfiguration

## SYNOPSIS
This cmdlet retrieves the global settings of the virtual switch from the Network Controller

## SYNTAX

```
Get-NetworkControllerVirtualSwitchConfiguration [-ConnectionUri <Uri>] [-CertificateThumbprint <String>]
 [-Credential <PSCredential>] [-PassInnerException] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet retrieves the global settings of the virtual switch from the Network Controller. This primarily retrieves Quality of Service settings for all virtual switches managed by the Network Controller.

## EXAMPLES

### Example 1

This example provides the virtual switch configuration of Network Controller, with REST endpoint as https://networkcontroller. The details of the configuration is present in the Properties resource.
```
Get-NetworkControllerVirtualSwitchConfiguration -ConnectionUri https://networkcontroller
```
## PARAMETERS

### -CertificateThumbprint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.This is the certificate thumbprint of the certificate.This thumbprint must also be provided in the *ClientCertificateThumbprint* parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

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

### -ConnectionUri
Specifies the Uniform Resource Identifier (URI) of the Network Controller, used by all Representational State Transfer (REST) clients to connect to Network Controller.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a user credential that has permission to perform this action.The default value is the current user.This user must be present in the security group provided in the *ClientSecurityGroup* parameter in the **Install-NetworkController** cmdlet.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassInnerException
This thumbprint must also be provided in the **ClientCertificateThumbprint** parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

The thumbprint must be provided only if the network controller client authentication is X509 certificates.
**Get-NetworkController** retrieves that client authentication and authorization information.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

Following properties can be retrieved for the virtual switch configuration:
1. Number of interfaces that have Quality of Service (QoS) enabled
2. Reservation mode for QoS: absolute or Weight
3. Link speed percentage
4. Default reservation for QoS
5. Whether hardware limits are enabled for QoS
6. Whether hardware reservations are enabled for QoS
7. Whether software reservations are enabled for QoS

## NOTES

## RELATED LINKS

