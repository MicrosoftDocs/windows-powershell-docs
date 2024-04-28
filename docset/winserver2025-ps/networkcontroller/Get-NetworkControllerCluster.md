---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-Help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollercluster?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerCluster
---

# Get-NetworkControllerCluster

## SYNOPSIS
Gets the network controller cluster settings.

## SYNTAX

```
Get-NetworkControllerCluster [-ComputerName <String>] [-UseSsl] [-Credential <PSCredential>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerCluster** cmdlet gets the network controller cluster settings such as cluster authentication settings, a list of nodes in the cluster, cluster version, and the certificate used to encrypt credentials.

## EXAMPLES

### Example 1: Get all network controller cluster settings
```
PS C:\> Get-NetworkControllerCluster
Version                        : 10.0.0
Node                           : {Node1, Node2, Node3}
ClusterAuthentication          : Kerberos
ManagementSecurityGroup        : Contoso\NCManagementAdmins
CredentialEncryptionCertificate: [Subject]
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
```

This command gets all network controller cluster settings.

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
Indicates that the network controller uses Secure Socket Layer (SSL).

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
- Cluster version
- Name of the Network Controller nodes
- Authentication to be used between cluster nodes
- Management security group
- Credential Encryption Certificate

## NOTES

## RELATED LINKS

[Install-NetworkControllerCluster](./Install-NetworkControllerCluster.md)

[Repair-NetworkControllerCluster](./Repair-NetworkControllerCluster.md)

[Set-NetworkControllerCluster](./Set-NetworkControllerCluster.md)

[Uninstall-NetworkControllerCluster](./Uninstall-NetworkControllerCluster.md)

