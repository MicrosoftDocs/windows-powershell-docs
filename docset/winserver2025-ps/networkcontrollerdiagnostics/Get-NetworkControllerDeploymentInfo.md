---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Debug-NetworkController.psm1-help.xml
Module Name: NetworkControllerDiagnostics
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontrollerdiagnostics/get-networkcontrollerdeploymentinfo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerDeploymentInfo
---

# Get-NetworkControllerDeploymentInfo

## SYNOPSIS
Queries the Network Controller for REST information.

## SYNTAX

```
Get-NetworkControllerDeploymentInfo [-NetworkController] <String> [[-Credential] <PSCredential>]
 [[-RestURI] <String>] [[-CertificateThumbprint] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerDeploymentInfo** cmdlet queries the Network Controller for Representational State Transfer (REST) information, such the REST URI and the REST Certificate.

You can run this cmdlet from a computer that has Layer-3 connectivity to the Network Controller.

## EXAMPLES

### Example 1: Get configuration state for all REST resources for a Network Controller
```
PS C:\>$Credential = Get-Credential
PS C:\> Get-NetworkControllerDeploymentInfo -NetworkController "NC-0.contoso.cloud.com" -Credential $Credential
```

The first command creates credentials by using the Get-Credential cmdlet, and then stores it in the $Credential variable.
The command prompts you for user name and password.

The second command gets configuration state for all REST resources for a Network Controller.

## PARAMETERS

### -CertificateThumbprint
Specifies certificate thumbprint to use for the Network Controller.
Specify this parameter for certificate deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a credential to use for the Network Controller.
Specify this parameter for Kerberos deployment.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkController
Specifies the name or IP address of a Network Controller node.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestURI
Specifies the URI to use for Network Controller REST APIs.
Specify this parameter for wildcard certificate deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
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

[Get-NetworkControllerReplica](./Get-NetworkControllerReplica.md)

