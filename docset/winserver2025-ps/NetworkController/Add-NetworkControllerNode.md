---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-Help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/add-networkcontrollernode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-NetworkControllerNode
---

# Add-NetworkControllerNode

## SYNOPSIS
Adds a network controller node to an existing network controller deployment.

## SYNTAX

```
Add-NetworkControllerNode -Name <String> -Server <String> -FaultDomain <String> -RestInterface <String>
 [-NodeCertificate <X509Certificate2>] [-Force] [-PassThru] [-CertificateSubjectName <String>]
 [-NodeCertificateFindBy <X509FindType>] [-ComputerName <String>] [-UseSsl] [-Credential <PSCredential>]
 [-CertificateThumbprint <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-NetworkControllerNode** cmdlet adds a network controller node to an existing network controller deployment.
If the existing computers in the deployment are not able to handle the load, this cmdlet can be used to scale up an existing deployment.
A two node deployment is not supported.
Therefore, if you are on a single node cluster and want to scale up, you must add at least two nodes to gain the benefits of high availability.

## EXAMPLES

### Example 1: Add network controller to an existing network controller deployment
```
PS C:\> Add-NetworkControllerNode -Name "Node1" -Server "NCNode1.contoso.com" -FaultDomain "fd:/rack1/host1" -RestInterface "Ethernet"
Name            : Node1
Server          : NCNode1.contoso.com
FaultDomain     : fd:/rack1/host1
RestInterface   : Ethernet
NodeCertificate :
Status          : Up
```

This command adds a network controller node named Node1 to the existing network controller deployment.
The FQDN of the computer is named NCNode1.contoso.com and the interface on the computer listening to REST requests is named Ethernet.

## PARAMETERS

### -CertificateSubjectName
Specifies the subject name of the certificate used to perform this action.

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

### -CertificateThumbprint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.
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

### -FaultDomain
Specifies the servers that are likely to experience failure at the same time due to shared physical dependencies such as power and networking sources.

Fault domains typically represent hierarchies that are related to these shared dependencies, with more servers likely to fail together from a higher point in the fault domain tree.
During runtime, network controllers enumerate the fault domains in the cluster and attempt to spread out the network controller services so that they are in separate fault domains.
This process helps ensure, in case of failure of any one fault domain, that the availability of that service and its state is not compromised.

Fault domains are specified in a hierarchical format.
For example: /DC1/Rack1/Host1, where DC1 is the datacenter name, Rack1 is the rack name and Host1 is the name of the host where the node is placed.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
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

### -Name
Specifies the friendly name of the computer to be added to the deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeCertificate
Specifies the certificate used for authenticating the computer.
You should only specify this parameter if the cluster is using certificate based authentication.

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

### -NodeCertificateFindBy
Specifies the method by which to find the node certificate.

```yaml
Type: X509FindType
Parameter Sets: (All)
Aliases:
Accepted values: FindByThumbprint, FindBySubjectName

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

### -RestInterface
Specifies the name of the interface on the node that will receive requests from Representational State Transfer (REST) clients.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Specifies the fully qualified domain name (FQDN), IP address, or hostname of the computer to be added to the deployment.
If Kerberos is being used for cluster authentication, the FQDN must be provided.

```yaml
Type: String
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
- Name of the node
- Hostname, FQDN, or IP address of the node
- Fault domain of the node
- Name of interface to be used for REST operations on the node
- Node certificate

## NOTES

## RELATED LINKS

[Disable-NetworkControllerNode](./Disable-NetworkControllerNode.md)

[Enable-NetworkControllerNode](./Enable-NetworkControllerNode.md)

[Get-NetworkControllerNode](./Get-NetworkControllerNode.md)

[Remove-NetworkControllerNode](./Remove-NetworkControllerNode.md)

[Set-NetworkControllerNode](./Set-NetworkControllerNode.md)

