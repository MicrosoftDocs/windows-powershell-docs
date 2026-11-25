---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-Help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/new-networkcontrollernodeobject?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetworkControllerNodeObject
---

# New-NetworkControllerNodeObject

## SYNOPSIS
Creates a network controller node object.

## SYNTAX

```
New-NetworkControllerNodeObject -Name <String> -Server <String> -FaultDomain <String> -RestInterface <String>
 [-NodeCertificate <X509Certificate2>] [-NodeCertificateFindBy <X509FindType>]
 [-CertificateSubjectName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetworkControllerNodeObject** cmdlet creates a network controller node object.
This cmdlet is used for configuring a network controller for the first time.
The object created from this cmdlet is passed to the **Install-NetworkControllerCluster** cmdlet to create a network controller cluster.

The steps for configuring a network controller are:

- Install the network controller role on all the computers that will be functioning as a network controller in your deployment.
- From one of those computers (or any other remote computer), run the **New-NetworkControllerNodeObject** cmdlet to enter the details of the node to be part of the deployment.
Repeat this step for all the computers that are part of the deployment.
These node objects will be passed as a parameter to the next cmdlet.
- Run the **Install-NetworkControllerCluster** cmdlet to create a new network controller cluster.
- Run the **Install-NetworkController** cmdlet to create the network controller application on top of the cluster.

## EXAMPLES

### Example 1: Create a network controller node object
```
PS C:\> New-NetworkControllerNodeObject -Name "Node1" -Server "NCNode1.contoso.com" -FaultDomain "fd:/rack1/host1" -RestInterface "Ethernet"
```

This command creates a network controller node object named Node1.
The fully qualified domain name of the computer is NCNode1.contoso.com and the interface on the computer listening to REST requests is named Ethernet.

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

### -FaultDomain
Specifies the servers that are likely to experience failure at the same time due to shared physical dependencies such as power and networking sources.

Fault domains typically represent hierarchies that are related to these shared dependencies, with more servers likely to fail together from a higher point in the fault domain tree.
During runtime, a network controller considers the fault domains in the cluster and attempts to spread out the network controller services so that they are in separate fault domains.
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

### -Name
Specifies the name of the computer to be added to the deployment.

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
You only need to specify this parameter if the cluster is using certificate based authentication.

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
Accepted values: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestInterface
Specifies the name of the interface on the node that will receive requests from the representational state transfer (REST) clients.

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
If Kerberos authentication is being used for cluster authentication, FQDN must be provided.

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

[Install-NetworkController](./Install-NetworkController.md)

[Install-NetworkControllerCluster](./Install-NetworkControllerCluster.md)

