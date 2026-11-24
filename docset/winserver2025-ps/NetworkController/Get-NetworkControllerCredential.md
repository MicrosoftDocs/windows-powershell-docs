---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollercredential?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerCredential
---

# Get-NetworkControllerCredential

## SYNOPSIS
Retrieves a specified device credential or all device credentials from Network Controller.

## SYNTAX

```
Get-NetworkControllerCredential [[-ResourceId] <String[]>] -ConnectionUri <Uri>
 [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerCredential** retrieves the details of a specified device credential from Network Controller.
Network Controller uses this device credential to connect to a southbound device for managing the device.

**Get-NetworkControllerCredential** retrieves the credential type, and if the credential type is composed of username and password, it retrieves only the user name of the credential.

## EXAMPLES

### Example 1: Get credential
```
PS C:\> Get-NetworkControllerCredential -ConnectionUri "https://restserver" -ResourceId "Cred1"

Tags             :

ResourceRef      : /credentials/cred1

CreatedTime      : 1/1/0001 12:00:00 AM

InstanceId       : e16ffe62-a701-4d31-915e-7234d4bc5a18

Etag             : W/"1ec59631-607f-4d3e-ac78-94b0822f3a9d"

ResourceMetadata :

ResourceId       : cred1

Properties       :Microsoft.Windows.NetworkController.CredentialProperties
```

This command retrieves a credential with ID cred1.

## PARAMETERS

### -CertificateThumbprint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.
This is the certificate thumbprint of the certificate.

This thumbprint must also be provided in the **ClientCertificateThumbprint** parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

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
Specifies the Uniform Resource Identifier (URI) of the Network Controller, used by all Representational State Transfer (REST) clients to connect to Network Controller.

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
The default value is the current user.This user must be present in the security group provided in the **ClientSecurityGroup** parameter in the **Install-NetworkController** cmdlet.

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

### -ResourceId
Specifies an array of one or more credentials to retrieve.
If **ResourceID** is not provided, all the credentials in the Network Controller will be retrieved.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

The output contains the following fields:
- Resource reference uri
- Created time of the resource
- Instance ID of the resource
- Resource Metadata
- Resource ID
- Properties of the resource

## NOTES

## RELATED LINKS

[Install-NetworkController](./Install-NetworkController.md)

[New-NetworkControllerCredential](./New-NetworkControllerCredential.md)

[Remove-NetworkControllerCredential](./Remove-NetworkControllerCredential.md)

[Set-NetworkController](./Set-NetworkController.md)

