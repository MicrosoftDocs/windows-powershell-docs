---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Debug-NetworkControllerConfigurationState-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Debug-NetworkControllerConfigurationState
ms.reviewer:
ms.assetid: 7C57F4E3-3DED-4CC7-AB85-D8308803D953
---

# Debug-NetworkControllerConfigurationState

## SYNOPSIS
Queries for resources in a failure or warning state.

## SYNTAX

```
Debug-NetworkControllerConfigurationState [-NetworkController] <String> [[-ResourceId] <String>]
 [[-ResourceType] <String>] [[-Credential] <PSCredential>] [[-RestURI] <String>]
 [[-CertificateThumbprint] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Debug-NetworkControllerConfigurationState** cmdlet queries for resources that are in a failure or warning state.
This cmdlet queries the Network Controller to see if there are any tenant or fabric resources that are in a failure or warning configuration state based on the actual configuration state of the component.
This cmdlet also returns detailed information that contains the source of the error, a message, and error code.

You can run this cmdlet from a computer that has Layer-3 connectivity to the Representational State Transfer (REST) IP address of the Network Controller.
The computer must have the Network Controller REST certificate installed.

## EXAMPLES

### Example 1: Query configuration state for REST resources
```
PS C:\>Debug-NetworkControllerConfigurationState -NetworkController 10.123.177.94
```

This command queries configuration state for all REST resources for the specified Network Controller.

## PARAMETERS

### -CertificateThumbprint
Specifies the certificate thumbprint to use for the Network Controller.
Specify this parameter for certificate deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a credential to use for the Network Controller.
To obtain a **PSCredential** object, use the Get-Credential cmdlet.
Specify this parameter for Kerberos deployment.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
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

### -ResourceId
Specifies a REST resource ID.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceType
Specifies a REST Resource type.

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

### -RestURI
Specifies the URI to use for Network Controller REST APIs.
Specify this parameter for wildcard certificate deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Debug-NetworkController](./Debug-NetworkController.md)

[Debug-ServiceFabricNodeStatus](./Debug-ServiceFabricNodeStatus.md)

