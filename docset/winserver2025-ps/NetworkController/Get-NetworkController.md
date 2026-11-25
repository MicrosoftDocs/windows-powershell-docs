---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-Help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontroller?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkController
---

# Get-NetworkController

## SYNOPSIS
Gets network controller application settings.

## SYNTAX

```
Get-NetworkController [-ComputerName <String>] [-UseSsl] [-Credential <PSCredential>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkController** cmdlet gets network controller application settings.
Use this cmdlet to obtain application version, names of the nodes in the deployment, client authentication settings, IP address for representational state transfer (REST) operations, and certificate for encryption between REST clients and the network controller.

## EXAMPLES

### Example 1: Get network controller application settings
```
PS C:\> Get-NetworkController
Node                            : {Node01, Node02, Node03}
ClientAuthentication            : Kerberos
ClientCertificateThumbprint     :
ClientSecurityGroup             : Contoso\RestClients
ServerCertificate                  : [Subject]
                                   CN=NCEncryption

                                  [Issuer]
                                    CN=Contoso

                                  [Serial Number]
                                    1C00000003786A607D6EFB733F000000000003

                                  [Not Before]
                                    2/11/2015 6:18:21 AM

                                  [Not After]
                                    2/10/2017 6:18:21 AM
                                  [Thumbprint]
                                    D4FDE4F607849083C590466334D66037C0E38001

RestIPAddress                   : 10.0.0.1/24
Version                         : 10.0.0
```

This command gets network controller application settings.

## PARAMETERS

### -CertificateThumbprint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.
Specify the certificate thumbprint of the certificate.
account that has permission to perform this action.
Specify the certificate thumbprint of the certificate.
Specify this parameter only if you run this cmdlet on a computer that is not part of the network controller cluster.

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

### -ComputerName
Specifies the name of the network controller node on which this cmdlet operates.

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

### -Credential
Specifies a user credential that has permission to perform this action.
The default is the current user.
Specify this parameter only if you run this cmdlet on a computer that is not part of the network controller cluster.

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

### -UseSsl
Indicates that the remote computer uses the Secure Sockets Layer (SSL) protocol to establish a connection to the Network Controller node.
The default value of this parameter is false.
Specify this parameter only if you run this cmdlet on a computer that is not part of the network controller cluster.

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

This cmdlet returns an object that contains the following fields:

- Names of the network controller nodes
- Authentication mode used between REST clients and the Network Controller
- Client security group
- Client certificate thumbprints
- SSL certificate that is used for encryption of data between REST clients and network controller
- REST IP address
- Application version

## NOTES

## RELATED LINKS

[Install-NetworkController](./Install-NetworkController.md)

[Set-NetworkController](./Set-NetworkController.md)

[Uninstall-NetworkController](./Uninstall-NetworkController.md)

