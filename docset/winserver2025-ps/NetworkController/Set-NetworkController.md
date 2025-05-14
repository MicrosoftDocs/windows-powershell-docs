---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-Help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/set-networkcontroller?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetworkController
---

# Set-NetworkController

## SYNOPSIS
Sets network controller application settings.

## SYNTAX

```
Set-NetworkController [-ClientAuthentication <ClientAuthentication>] [-ClientCertificateThumbprint <String[]>]
 [-ClientSecurityGroup <String>] [-ServerCertificate <X509Certificate2>] [-RestIPAddress <String>]
 [-RestName <String>] [-PassThru] [-ComputerName <String>] [-UseSsl] [-Credential <PSCredential>]
 [-CertificateThumbprint <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetworkController** cmdlet sets network controller application settings.
You can modify the following settings:

- Client authentication mode.
- Client security group.
If the client authentication mode is Kerberos, you must specify a client security group.
- Client certificate thumbprints.
If the client authentication mode is x509, you must specify certificate thumbprints.
- The IP address that network controller uses for representational state transfer (REST) communication.
- Secure Sockets Layer (SSL) certificate that network controller uses for encrypting the communication between the REST clients and the network controller, as well as to secure communication with southbound clients.

## EXAMPLES

### Example 1: Change the authentication mode for clients
```
PS C:\> Set-NetworkController -ClientAuthentication Kerberos -ClientSecurityGroup "Contoso\RestClients" -PassThru
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

This command changes the authentication mechanism between REST clients and network controller to Kerberos.
In order to change the authentication mode to Kerberos, you must also specify the *ClientSecurityGroup* parameter.

### Example 2: Change the REST IP address
```
PS C:\> Set-NetworkController -RestIPAddress 10.0.0.1/24
```

This command changes the REST IP address to 10.0.0.1.
This command requires that the subnet mask be specified in the IP address.

## PARAMETERS

### -CertificateThumbprint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.
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

### -ClientAuthentication
Specifies the type of authentication that network controller uses to communicate with REST clients.
The acceptable values for this parameter are:

- Kerberos
- X509
- None

If the clients and network controller computers are domain joined, you should specify Kerberos authentication.
Otherwise, specify X509 authentication.
We do not recommend a value of None for production environments.

```yaml
Type: ClientAuthentication
Parameter Sets: (All)
Aliases:
Accepted values: None, Kerberos, X509

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientCertificateThumbprint
Specifies an array of thumbprints of the certificates of REST clients that can communicate with the network controller.
Specify this parameter only if the value of the *ClientAuthentication* parameter is X509.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientSecurityGroup
Specifies the security group that contains the name of the REST clients that can communicate with the network controller.
Specify this parameter only if the value of the *ClientAuthentication* parameter is Kerberos.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -RestIPAddress
Specifies the IP address on which network controller nodes communicate with the REST clients.
This IP address must not be an existing IP address on any of the network controller nodes.

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

### -RestName
Specifies the DNS name of the Network Controller cluster.
This must be specified if the Network Controller nodes are in different subnets.
In this case, you must also enable dynamic registration of the RestName on the DNS servers.

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

### -ServerCertificate
Specifies the certificate to use to encrypt communication between network controller and REST clients, and also to secure communication between Network Controller and the southbound clients.
This certificate must have Server Authentication EKU and should be trusted by the REST clients.
Also, the certificate subject name or subject alternative name (SAN) must resolve to the REST IP address in DNS.

```yaml
Type: X509Certificate2
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
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
- Authentication mode used between Network Controller and the REST clients
- Client security group
- Client certificate thumbprints
- SSL certificate that is used for encryption of data between REST clients and network controller
- REST IP address
- Application version

## NOTES

## RELATED LINKS

[Get-NetworkController](./Get-NetworkController.md)

[Install-NetworkController](./Install-NetworkController.md)

[Uninstall-NetworkController](./Uninstall-NetworkController.md)

