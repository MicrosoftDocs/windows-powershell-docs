---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-Help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/set-networkcontrollercluster?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetworkControllerCluster
---

# Set-NetworkControllerCluster

## SYNOPSIS
Sets a network controller cluster.

## SYNTAX

```
Set-NetworkControllerCluster [-ManagementSecurityGroup <String>]
 [-CredentialEncryptionCertificate <X509Certificate2>] [-EnableAutomaticUpdates <Boolean>] [-PassThru] [-Force]
 [-UseSubjectNameForNodeCert <Boolean>] [-ComputerName <String>] [-UseSsl] [-Credential <PSCredential>]
 [-CertificateThumbprint <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetworkControllerCluster** cmdlet sets a network controller cluster.
After a cluster is deployed, you can use this cmdlet to set the management security group (if Kerberos authentication is used), and the certificate to encrypt the credentials stored on disk.
Cluster authentication, once set, cannot be changed for the deployment.

## EXAMPLES

### Example 1: Change the management security group for cluster authentication
```
PS C:\> Set-NetworkControllerCluster -ManagementSecurityGroup "Contoso\NCUsers" -PassThru
Version                        : 10.0.0
Node                           : {Node1, Node2, Node3}
ClusterAuthentication          : Kerberos
ManagementSecurityGroup        : Contoso\NCUsers
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

This command changes the management security group for cluster authentication to Contoso\NCUsers.

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

### -CredentialEncryptionCertificate
Specifies the certificate that is used to encrypt the credentials used to access the Network Controller binaries on disk and *LogLocationCredential* parameter.
You must specify this parameter if you specify the *LogLocationCredential* parameter.

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

### -EnableAutomaticUpdates
Specifies whether to enable automatic updates for the cluster.

```yaml
Type: Boolean
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

### -ManagementSecurityGroup
Specifies the security group for users that have permission to run the network controller deployment cmdlets.
You must specify this parameter if the cluster uses Kerberos authentication.

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

### -UseSubjectNameForNodeCert
Specifies whether to use the subject name for the node certificate.

```yaml
Type: Boolean
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
- Cluster version
- Name of the network controller nodes
- Authentication to use between cluster nodes
- Management security group
- Credential encryption certificate

## NOTES

## RELATED LINKS

[Get-NetworkControllerCluster](./Get-NetworkControllerCluster.md)

[Install-NetworkControllerCluster](./Install-NetworkControllerCluster.md)

[Repair-NetworkControllerCluster](./Repair-NetworkControllerCluster.md)

[Uninstall-NetworkControllerCluster](./Uninstall-NetworkControllerCluster.md)

