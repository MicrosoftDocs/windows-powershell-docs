---
description: The Get-NetworkControllerDiscovery cmdlet gets the network controller version and the versions of URIs supported by the controller.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 09/27/2021
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollerdiscovery?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerDiscovery
---

# Get-NetworkControllerDiscovery

## SYNOPSIS
Gets the network controller version and the versions of URIs supported by the controller.

## SYNTAX

```
Get-NetworkControllerDiscovery [-ConnectionUri <Uri>] [-CertificateThumbprint <String>]
 [-Credential <PSCredential>] [-PassInnerException] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerDiscovery** cmdlet gets the network controller version and the versions of URIs supported by the controller.

## EXAMPLES

### Example 1: Get network controller discovery objects
```powershell
Get-NetworkControllerDiscovery -ConnectionUri https://networkcontroller
```

This example gets the network controller version and the versions of URIs supported by the specified controller.

## PARAMETERS

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

### -ConnectionUri
Specifies the Uniform Resource Identifier (URI) of the Network Controller that all Representational State Transfer (REST) clients use to connect to that controller.

```yaml
Type: Uri
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
The default value is the current user.

This user must be present in the security group provided in the **ClientSecurityGroup** parameter in the `Install-NetworkController` cmdlet.
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

### -PassInnerException
This thumbprint must also be provided in the **ClientCertificateThumbprint** parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

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

[Get-NetworkControllerAuditingSettingsConfiguration](Get-NetworkControllerAuditingSettingsConfiguration.md)
