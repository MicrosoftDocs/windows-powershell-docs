---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-Help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/set-networkcontrollernode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetworkControllerNode
---

# Set-NetworkControllerNode

## SYNOPSIS
Sets a node in a network controller cluster.

## SYNTAX

```
Set-NetworkControllerNode -Name <String> [-RestInterface <String>] [-NodeCertificate <X509Certificate2>]
 [-PassThru] [-Force] [-ComputerName <String>] [-UseSsl] [-Credential <PSCredential>]
 [-CertificateThumbprint <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetworkControllerNode** cmdlet changes the settings of a node in a network controller cluster.
Use this cmdlet to modify the settings for the interface on which the node listens for representational state transfer (REST) requests, and to set the node certificate.

## EXAMPLES

### Example 1: Set the REST interface for a network controller node
```
PS C:\> Set-NetworkControllerNode -Name "Node1" -RestInterface "Corpnet" -PassThru
Name            : Node1
Server          : NCNode1.contoso.com
FaultDomain     : fd:/rack1/host1
RestInterface   : Corpnet
NodeCertificate :
Status          : Up
```

This command sets the REST interface to Corpnet for the node named Node1.

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
Specifies the name of a node.
This cmdlet updates the settings for the node that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NodeCertificate
Specifies the certificate to use to authenticate a computer.
You should only specify this parameter if the cluster uses certificate-based authentication.

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
Specifies the name of the interface on the node that receives requests from REST clients.

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

### System.String

## OUTPUTS

### System.Object

This cmdlet returns an object that contains the following fields:
- Name of the node
- Hostname, fully qualified domain name (FQDN), or IP address of the node
- Fault domain of the node
- Name of interface to use for REST operations on the node
- Node certificate

## NOTES

## RELATED LINKS

[Add-NetworkControllerNode](./Add-NetworkControllerNode.md)

[Disable-NetworkControllerNode](./Disable-NetworkControllerNode.md)

[Enable-NetworkControllerNode](./Enable-NetworkControllerNode.md)

[Get-NetworkControllerNode](./Get-NetworkControllerNode.md)

[Remove-NetworkControllerNode](./Remove-NetworkControllerNode.md)

