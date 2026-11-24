---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-Help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/repair-networkcontrollercluster?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Repair-NetworkControllerCluster
---

# Repair-NetworkControllerCluster

## SYNOPSIS
Repairs the network controller to bring it out of quorum loss.

## SYNTAX

```
Repair-NetworkControllerCluster [-ComputerName <String>] [-UseSsl] [-Credential <PSCredential>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Repair-NetworkControllerCluster** cmdlet is used in a scenario when a majority of nodes in the network controller deployment become unavailable, thus causing quorum loss for the deployment

As quorum is lost, the remaining nodes lose consistency and up-to-date data.
When a quorum loss occurs, the network controller will stop functioning.
If you have deployed System Center Operations Manager for network controller monitoring, you will be able to see a red alert on the Operations Manager console.
If you are not using Operations Manager, you will see critical events in the network controller event channels on the nodes that describe the problem.
When this happens, you must bring the unreachable nodes up or add additional nodes to the deployment so that quorum can be restored.
After this, you have to run this cmdlet so that the network controller can internally do a consistency check on the data and state inside the controller system.
After the consistency check is complete, the network controller will enable its services and start working.

## EXAMPLES

### Example 1: Repair a network controller cluster
```
PS C:\> Repair-NetworkControllerCluster -ComputerName "Node1.Contoso.com"
```

This command repairs a network controller cluster, to bring it out of quorum loss.
The cluster is identified by Node1.Contoso.com, which is a node in the cluster.

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
Indicates that the remote computer uses Secure Socket Layer (SSL) protocol to establish a connection to the network controller node.
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

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-NetworkControllerCluster](./Get-NetworkControllerCluster.md)

[Install-NetworkControllerCluster](./Install-NetworkControllerCluster.md)

[Set-NetworkControllerCluster](./Set-NetworkControllerCluster.md)

[Uninstall-NetworkControllerCluster](./Uninstall-NetworkControllerCluster.md)

