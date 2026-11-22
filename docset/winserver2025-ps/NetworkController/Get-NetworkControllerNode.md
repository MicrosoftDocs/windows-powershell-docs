---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-Help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollernode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerNode
---

# Get-NetworkControllerNode

## SYNOPSIS
Gets the network controller node settings.

## SYNTAX

```
Get-NetworkControllerNode [-Name <String>] [-ComputerName <String>] [-UseSsl] [-Credential <PSCredential>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerNode** cmdlet gets the network controller node settings such as the node name, fully qualified domain name (FQDN), IP address, fault domain, representational state transfer (REST) interface of the node, and the node certificate, if applicable.

## EXAMPLES

### Example 1: Get all network controller nodes in a deployment
```
PS C:\> Get-NetworkControllerNode
Name            : Node1
Server          : NCNode1.contoso.com
FaultDomain     : fd:/host1/node1
RestInterface   : Ethernet
NodeCertificate :
Status          : Up
Name            : Node2
Server          : NCNode2.contoso.com
FaultDomain     : fd:/host2/node2
RestInterface   : Ethernet
NodeCertificate :
Status          : Up
Name            : Node3
Server          : NCNode3.contoso.com
FaultDomain     : fd:/host3/node3
RestInterface   : Ethernet
NodeCertificate :
Status          : Up
```

This command gets the network controller node settings for all nodes in the deployment.

### Example 2: Get network controller node settings for a specified node by name
```
PS C:\> Get-NetworkControllerNode -Name "Node1"
Node1Name       : Node1
Server          : NCNode1.contoso.com
FaultDomain     : fd:/host1/node1
RestInterface   : Ethernet
NodeCertificate :
Status          : Up
```

This command gets the network controller node settings for a specific node named Node1.

## PARAMETERS

### -CertificateThumbprint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.
This is the certificate thumbprint of the certificate.
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

### -Name
Specifies the friendly name of the node for the network controller.
If not provided, settings are retrieved for all nodes in the deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.String

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

[Add-NetworkControllerNode](./Add-NetworkControllerNode.md)

[Disable-NetworkControllerNode](./Disable-NetworkControllerNode.md)

[Enable-NetworkControllerNode](./Enable-NetworkControllerNode.md)

[Remove-NetworkControllerNode](./Remove-NetworkControllerNode.md)

[Set-NetworkControllerNode](./Set-NetworkControllerNode.md)

