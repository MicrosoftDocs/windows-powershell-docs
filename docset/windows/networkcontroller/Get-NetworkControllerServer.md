---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-NetworkControllerServer
ms.reviewer:
ms.assetid: 97766CFD-A085-496B-8B76-7C3D1A64E699
---

# Get-NetworkControllerServer

## SYNOPSIS
Gets configuration of a physical host from the Network Controller.

## SYNTAX

```
Get-NetworkControllerServer [[-ResourceId] <String[]>] -ConnectionUri <Uri> [-CertificateThumbprint <String>]
 [-Credential <PSCredential>] [-PassInnerException] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerServer** cmdlet gets configuration of a physical host from the Network Controller.
For a host to be managed by the Network Controller, you must add it to the Network Controller by using **New-NetworkControllerServer** cmdlet.

## EXAMPLES

### Example 1: Get server configuration
```
PS C:\> Get-NetworkControllerServer -ConnectionUri "https://networkcontroller" -ResourceId "Server01"
```

This command retrieves the configuration of a server that has the resource ID Server01, from the Network Controller.

## PARAMETERS

### -CertificateThumbprint
Specifies the certificate thumbprint of a digital public key X.509 certificate of a user account that has permission to perform this action.
In order for Network Controller to authorize the account, specify this thumbprint by using the *ClientCertificateThumbprint* parameter of the **Install-NetworkController** or **Set-NetworkController** cmdlet.

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

### -ConnectionUri
Specifies the Uniform Resource Identifier (URI) of the Network Controller.
All Representational State Transfer (REST) clients use this URI to connect to Network Controller.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a user credential that has permission to perform this action.
The default value is the current user.
This user must be present in the security group specified in the *ClientSecurityGroup* parameter in **Install-NetworkController**.

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

### -PassInnerException


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

### -ResourceId
Specifies an array of resource IDs of servers for which this cmdlet gets settings.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
This cmdlet returns an object that contains the following configuration settings: 

- Connections that specify the information that is required to connect to the server for the purposes of managing it.
Each connection has a management address and a credential reference to connect to the server. 
- Model number. 
- Array of physical network interfaces on the server. 
- Operating system that runs on the server. 
- Slot in the rack that contains the server. 
- Serial number. 
- Server vendor name. 
- Virtual servers that are on the server and are being managed by Network Controller. 
- Virtual switches that are on the server and are being managed by Network Controller.

## NOTES

## RELATED LINKS

[New-NetworkControllerServer](./New-NetworkControllerServer.md)

[Remove-NetworkControllerServer](./Remove-NetworkControllerServer.md)

[Install-NetworkController](./Install-NetworkController.md)

[Set-NetworkController](./Set-NetworkController.md)

