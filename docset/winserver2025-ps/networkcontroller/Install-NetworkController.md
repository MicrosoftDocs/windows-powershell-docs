---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-Help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/install-networkcontroller?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-NetworkController
---

# Install-NetworkController

## SYNOPSIS
Creates a network controller application on top of the network controller cluster.

## SYNTAX

```
Install-NetworkController -Node <NetworkControllerNode[]> -ClientAuthentication <ClientAuthentication>
 [-ClientCertificateThumbprint <String[]>] [-ClientSecurityGroup <String>]
 -ServerCertificate <X509Certificate2> [-RestIPAddress <String>] [-RestName <String>] [-Force]
 [-ComputerName <String>] [-UseSsl] [-Credential <PSCredential>] [-CertificateThumbprint <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Install-NetworkController** cmdlet creates a network controller application on the network controller cluster.
After you run this cmdlet, the network controller is running.

The steps for configuring a network controller are as follows:

- Install the network controller role on all the computers that will be functioning as a network controller in your deployment.
- From one of those computers (or any other remote computer), run the **New-NetworkControllerNodeObject** cmdlet to enter the details of the node to be part of the deployment.
Repeat this step for all the computers that are part of the deployment.
These node objects will be passed as a parameter to the next cmdlet.
- Run the **Install-NetworkControllerCluster** cmdlet to create a new network controller cluster.
- Run the **Install-NetworkController** cmdlet to create the network controller application on top of the cluster.

## EXAMPLES

### Example 1: Create a network controller in a test environment
```
PS C:\> $NodeObject = New-NetworkControllerNodeObject -Name "Node01" -Server "NCNode11" -FaultDomain "fd:/rack1/host1" -RestInterface Ethernet
PS C:\> $Certificate = Get-Item Cert:\LocalMachine\My | Get-ChildItem | where {$_.Subject -imatch "NCEncryption" }
PS C:\> Install-NetworkControllerCluster -Node $NodeObject -ClusterAuthentication None
PS C:\> Install-NetworkController -Node $NodeObject -ClientAuthentication None -RestIpAddress "10.0.0.1/24" -ServerCertificate $Certificate
Node                            : {Node01}
ClientAuthentication            : None
ClientCertificateThumbprint     :
ClientSecurityGroup             :
ServerCertificate               : [Subject]
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

The first command creates a network controller node object, and then stores it in the $NodeObject variable.

The second command gets a certificate named NCEncryption, and then stores it in the $Certificate variable.
The command uses standard Windows PowerShell® cmdlets.
For more information, type `Get-Help Get-Item`, `Get-Help Get-ChildItem`, and `Get-Help Where`.

The third command creates a network controller cluster by using the **Install-NetworkControllerCluster** cmdlet.
The cluster contains the node object stored in $NodeObject.

The final command deploys the network controller in a test environment.
Since single node is used in the deployment, there is no high availability support.
This network controller employs no authentication between the cluster nodes, or between the REST clients and network controller.
The command specifies the $Certificate to encrypt the traffic between the REST clients and network controller.

### Example 2: Create a network controller in a domain joined environment
```
PS C:\> $Node01 = New-NetworkControllerNodeObject -Name "Node01" -Server "NCNode01.Contoso.com" -FaultDomain "fd:/rack1/host1" -RestInterface Ethernet
PS C:\> $Node02 = New-NetworkControllerNodeObject -Name "Node02" -Server "NCNode02.Contoso.com" -FaultDomain "fd:/rack1/host2" -RestInterface Ethernet
PS C:\> $Node03 = New-NetworkControllerNodeObject -Name "Node03" -Server "NCNode03.Contoso.com" -FaultDomain "fd:/rack2/host3" -RestInterface Ethernet
PS C:\> $Certificate = Get-Item Cert:\LocalMachine\My | Get-ChildItem | where {$_.Subject -imatch "NCEncryption" }
PS C:\> Install-NetworkControllerCluster -Node @($Node01,$Node02,$Node03) -ClusterAuthentication Kerberos -ManagementSecurityGroup "Contoso\NCManagementAdmins" -LogLocation "\\share\diagnostics" -CredentialEncryptionCertificate $Certificate
PS C:\> Install-NetworkController -Node @($Node01,$Node02,$Node03) -ClientAuthentication Kerberos -ClientSecurityGroup "Contoso\RestClients" -RestIpAddress "10.0.0.1/24" -StoreCertificate $Certificate -EnableAllLogs
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

The first three commands create network controller node objects, and then stores them in the $Node01, $Node02, and $Node03 variables.

The fourth command gets a certificate named NCEncryption, and then stores it in the $Certificate variable.
The command uses standard cmdlets.

The fifth command creates a network controller cluster by using the **Install-NetworkControllerCluster** cmdlet.
The cluster contains the node objects stored in the variables.

The final command deploys the network controller in a domain joined environment.
Network controller uses Kerberos authentication between the cluster nodes, and between the REST clients and network controller.
Only clients that are part of the RestClients security group can communicate with the network controller.
The certificate in $Certificate is used to encrypt traffic between the REST clients and network controller.

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
Specifies the type of authentication that network controller uses to communicate with representational state transfer (REST) clients.
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

Required: True
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

### -Node
Specifies an array of network controller nodes.
You can create the node objects by using **New-NetworkControllerNodeObject** cmdlet.

```yaml
Type: NetworkControllerNode[]
Parameter Sets: (All)
Aliases:

Required: True
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
Specifies the certificate to use to encrypt communication between the network controller and REST clients, as well as communication between the network controller and southbound clients.
This certificate must have Server Authentication EKU and should be trusted by the REST clients.
Also, the certificate subject name or subject alternative name (SAN) must resolve to the REST IP address in DNS

```yaml
Type: X509Certificate2
Parameter Sets: (All)
Aliases:

Required: True
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
- Authentication mode used between cluster nodes
- Client security group
- Client certificate thumbprints
- Server certificate that is used for encryption of data between the network controller and REST and southbound clients.
- REST IP address
- Application version

## NOTES

## RELATED LINKS

[Get-NetworkController](./Get-NetworkController.md)

[Set-NetworkController](./Set-NetworkController.md)

[Uninstall-NetworkController](./Uninstall-NetworkController.md)

[New-NetworkControllerNodeObject](./New-NetworkControllerNodeObject.md)

[Install-NetworkControllerCluster](./Install-NetworkControllerCluster.md)

