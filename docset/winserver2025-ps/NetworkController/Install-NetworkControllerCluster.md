---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-Help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/install-networkcontrollercluster?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-NetworkControllerCluster
---

# Install-NetworkControllerCluster

## SYNOPSIS
Creates a Network Controller cluster.

## SYNTAX

```
Install-NetworkControllerCluster -Node <NetworkControllerNode[]> -ClusterAuthentication <ClusterAuthentication>
 [-ManagementSecurityGroup <String>] [-DiagnosticLogLocation <String>] [-LogLocationCredential <PSCredential>]
 [-CredentialEncryptionCertificate <X509Certificate2>] [-GmsaAccountName <String>]
 [-LogTimeLimitInDays <UInt32>] [-LogSizeLimitInMBs <UInt32>] [-EnableAutomaticUpdates <Boolean>] [-Force]
 [-UseSsl] [-Credential <PSCredential>] [-CertificateThumbprint <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Install-NetworkControllerCluster** cmdlet creates a Network Controller cluster.
Configuration of the Network Controller involves creating a Network Controller cluster and then creating a Network Controller application on top of the cluster.
You can create a Network Controller application by calling the **Install-NetworkController** cmdlet.

You can configure a Network Controller using the following steps:

- Install the Network Controller role on all the computers that will be Network Controllers in your deployment.
- Run the **New-NetworkControllerNodeObject** cmdlet to enter the details of the node.
Repeat this step for all the computers that belong to the deployment.
The next step uses these node objects.
- Run the **Install-NetworkControllerCluster** cmdlet to create a Network Controller cluster.
- Run the **Install-NetworkController** cmdlet to create the Network Controller application for the cluster.

## EXAMPLES

### Example 1: Install a Network Controller cluster in a test deployment
```
PS C:\> $NodeObject = New-NetworkControllerNodeObject -Name "Node1" -Server "NCNode1" -FaultDomain "fd:/rack1/host1" -RestInterface "Ethernet"
PS C:\> Install-NetworkControllerCluster -Node $NodeObject -ClusterAuthentication None
Version                         : 10.0.0
Node                            : {Node1}
ClusterAuthentication           : None
ManagementSecurityGroup         :
CredentialEncryptionCertificate :
```

This command installs a Network Controller cluster in a test deployment.
High availability support is not present because a single node is used in the deployment.
No authentication is used between the cluster nodes.
Additionally, debug logs are stored locally.

### Example 2: Install a Network Controller cluster in a domain-joined environment
```
PS C:\> $NodeObject1 = New-NetworkControllerNodeObject -Name "Node1" -Server "NCNode1.Contoso.com" -FaultDomain "fd:/rack1/host1" -RestInterface "Ethernet"
PS C:\> $NodeObject2 = New-NetworkControllerNodeObject -Name "Node2" -Server "NCNode2.Contoso.com" -FaultDomain "fd:/rack1/host2" -RestInterface "Ethernet"
PS C:\> $NodeObject3 = New-NetworkControllerNodeObject -Name "Node3" -Server "NCNode3.Contoso.com" -FaultDomain "fd:/rack2/host3" -RestInterface "Ethernet"
PS C:\> $Certificate = Get-Item Cert:\LocalMachine\My | Get-ChildItem | where {$_.Subject -imatch "NCEncryption"}
PS C:\> Install-NetworkControllerCluster -Node @($NodeObject1,$NodeObject2,$NodeObject3) -ClusterAuthentication Kerberos -ManagementSecurityGroup Contoso\NCManagementAdmins -LogLocation "\\share\diagnostics" -CredentialEncryptionCertificate $Certificate
CertificateVersion             : 10.0.0
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

This command installs a Network Controller cluster in a domain-joined environment.
The authentication that is used between the cluster nodes is Kerberos.
Debug logs are stored in a central location.
To encrypt the credentials used to store Network Controller binaries on disk, the user provides a certificate with subject name as NCEncryption.

### Example 3: Install a Network Controller cluster in a non domain-joined environment
```
PS C:\> $Node1Certificate = Get-Item Cert:\LocalMachine\My | Get-ChildItem | where {$_.Subject -imatch "NCNode1"
PS C:\> $Node2Certificate = Get-Item Cert:\LocalMachine\My | Get-ChildItem | where {$_.Subject -imatch "NCNode2"
PS C:\> $Node3Certificate = Get-Item Cert:\LocalMachine\My | Get-ChildItem | where {$_.Subject -imatch "NCNode3"
PS C:\> $NodeObject1 = New-NetworkControllerNodeObject -Name "Node1" -Server "NCNode1" -FaultDomain "fd:/rack1/host1" -RestInterface "Ethernet" -Certificate $Node1Certificate
PS C:\> $NodeObject2 = New-NetworkControllerNodeObject -Name "Node2" -Server "NCNode2" -FaultDomain "fd:/rack1/host2" -RestInterface "Ethernet" -Certificate $Node2Certificate
PS C:\> $NodeObject3 = New-NetworkControllerNodeObject -Name "Node3" -Server "NCNode3" -FaultDomain "fd:/rack2/host3" -RestInterface "Ethernet" -Certificate $Node3Certificate
PS C:\> $Cert = Get-Item Cert:\LocalMachine\My |  Get-ChildItem | where {$_.Subject -imatch "NCEncryption"}
PS C:\> Install-NetworkControllerCluster -Node @($NodeObject1,$NodeObject2,$NodeObject3) -ClusterAuthentication x509-LogLocation "\\share\diagnostics" -StoreAccessCredential $Cred -CredentialEncryptionCertificate $Cert
Version                        : 10.0.0
Node                           : {Node1, Node2, Node3}
ClusterAuthentication          : x509
ManagementSecurityGroup        :
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

This command installs a Network Controller cluster in a non-domain-joined environment.
The authentication used between the cluster nodes is a X.509 certificate.
Debug logs are stored in a central location.
To encrypt the credentials used to store Network Controller binaries on disk, you have to provide a certificate with a subject name as NCEncryption.

## PARAMETERS

### -CertificateThumbprint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.
Specify the certificate thumbprint of the certificate.
Specify this parameter if you run this cmdlet on computer that is not part of the Network Controller cluster.

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

### -ClusterAuthentication
Specifies the type of authentication to be used amongst the cluster nodes.
The allowed values are Kerberos, x509, and None.
If the Network Controller nodes are domain joined, Kerberos authentication should be used.
If not, domain joined, x509 authentication should be used.
It is not recommended to deploy a cluster with no authentication in production environments.

```yaml
Type: ClusterAuthentication
Parameter Sets: (All)
Aliases:
Accepted values: None, Kerberos, X509

Required: True
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
Specify this parameter if you run this cmdlet on a computer that is not part of the Network Controller cluster.

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
Specifies the certificate to use to encrypt the credentials that are used to access Network Controller binaries on the disk.
It is also used to encrypt the *LogLocationCredential* if the administrator provides it.
This is mandatory if the *LogLocationCredential* is provided.

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

### -DiagnosticLogLocation
Specifies the location of diagnostic logs.

If you do not specify a value for this parameter, the logs are stored locally on each node.
Application logs are stored locally in the %systemdrive%\Windows\tracing\SDNDiagnostics folder.
Cluster logs are stored locally in %systemdrive%\ProgramData\Microsoft\Service Fabric\log\Traces folder.

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

### -GmsaAccountName
Specifies the name of the Group Managed Service Account (gMSA).

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

### -LogLocationCredential
Specifies the credentials to access the remote log location.
This is required only if the log location restricts access to few accounts.

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

### -LogSizeLimitInMBs
Specifies the maximum log size, in MB, to store.
Logs are stored in circular fashion.
If the *DiagnosticLogLocation* parameter is provided, the default value of this parameter is 40 GB.
If *DiagnosticLogLocation* is not provided, the logs are stored on the Network Controller nodes and the default value of this parameter is 15 GB.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogTimeLimitInDays
Specifies the duration limit, in days, for which the logs are stored.
Logs are stored in circular fashion.
The default value of this parameter is 3 days.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementSecurityGroup
Specifies the security group for users that have permission to execute the Network Controller deployment cmdlets.
This parameter is applicable and mandatory only if the cluster authentication is Kerberos.

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

### -Node
Specifies a list of Network Controller nodes.
You can create the node objects using **New-NetworkControllerNodeObject** cmdlet.

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

### -UseSsl
Indicates that the remote computer uses the Secure Sockets Layer (SSL) protocol to establish a connection to the Network Controller node.
The default value of this parameter is $False.
Specify this parameter only if you run this cmdlet on a computer that is not part of the Network Controller cluster.

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
- Cluster version
- Name of the Network Controller nodes
- Authentication to be used between cluster nodes
- Management security group
- Credential Encryption Certificate

## NOTES

## RELATED LINKS

[Get-NetworkControllerCluster](./Get-NetworkControllerCluster.md)

[Install-NetworkController](./Install-NetworkController.md)

[New-NetworkControllerNodeObject](./New-NetworkControllerNodeObject.md)

[Repair-NetworkControllerCluster](./Repair-NetworkControllerCluster.md)

[Set-NetworkControllerCluster](./Set-NetworkControllerCluster.md)

[Uninstall-NetworkControllerCluster](./Uninstall-NetworkControllerCluster.md)

