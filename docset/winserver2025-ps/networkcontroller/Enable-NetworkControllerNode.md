---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-Help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/enable-networkcontrollernode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-NetworkControllerNode
---

# Enable-NetworkControllerNode

## SYNOPSIS
Enables a network controller node.

## SYNTAX

```
Enable-NetworkControllerNode -Name <String> [-PassThru] [-IntentRejoin] [-ComputerName <String>] [-UseSsl]
 [-Credential <PSCredential>] [-CertificateThumbprint <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-NetworkControllerNode** cmdlet enables a disabled network controller node that used the **Disable-NetworkControllerNode** cmdlet.
After a network controller node is enabled, it will be able to process requests.

## EXAMPLES

### Example 1: Enable a network controller
```
PS C:\> Enable-NetworkControllerNode -Name "Node1" -PassThru
Name           : Node1
Server         : Node1.contoso.com
FaultDomain    : fd:/host1/node1
RestInterface  : Ethernet
NodeCertificate:
Status         : Enabling
```

This command enables the network controller node named Node1.

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

### -IntentRejoin
Indicates the intent to rejoin.

Use this parameter after cleaning up a node, for instance, if the node OS was replaced and the node is clean.
The service fabric application data repopulates using information from the computer whose name is specified.

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
Specifies the name of the node to be enabled.

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

The output for this cmdlet contains the following fields:
- Name of the node
- Hostname, fully qualified domain name (FQDN), or IP address of the node
- Fault domain of the node
- Name of interface to be used for representational state transfer (REST) operations on the node
- Node certificate
- Status of the node

## NOTES

## RELATED LINKS

[Add-NetworkControllerNode](./Add-NetworkControllerNode.md)

[Disable-NetworkControllerNode](./Disable-NetworkControllerNode.md)

[Get-NetworkControllerNode](./Get-NetworkControllerNode.md)

[Set-NetworkControllerNode](./Set-NetworkControllerNode.md)

