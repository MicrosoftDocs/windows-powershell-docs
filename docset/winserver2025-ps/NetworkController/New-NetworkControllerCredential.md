---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/new-networkcontrollercredential?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetworkControllerCredential
---

# New-NetworkControllerCredential

## SYNOPSIS
Adds or modifies a device credential in Network Controller.

## SYNTAX

```
New-NetworkControllerCredential [-ResourceId] <String> [[-Tags] <PSObject>]
 [-Properties] <CredentialProperties> [[-Etag] <String>] [[-ResourceMetadata] <ResourceMetadata>] [-Force]
 -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetworkControllerCredential** cmdlet adds a new device credential to the Network Controller.
If the credential is already present, this cmdlet will modify the properties of the credential.
Network Controller uses the device credential to connect to a southbound device for managing the device.
This cmdlet adds or modifies credentials based on username and password, Simple Network Management Protocol (SNMP)-based credentials and certificate-based credentials.

## EXAMPLES

### Example 1: Create a network credential
```
PS C:\> $cred=New-Object Microsoft.Windows.Networkcontroller.credentialproperties
$cred.type="usernamepassword"
$cred.username="admin"
$cred.value="abcd"

New-NetworkControllerCredential -ConnectionUri "https://restserver" -Properties $Cred -ResourceId "Cred1"



Tags             :

ResourceRef      : /credentials/cred1

CreatedTime      : 1/1/0001 12:00:00 AM

InstanceId       : e16ffe62-a701-4d31-915e-7234d4bc5a18

Etag             : W/"0b90d8d3-5591-47a1-b2eb-474314fdb8f6"

ResourceMetadata :

ResourceId       : cred1

Properties       : Microsoft.Windows.NetworkController.CredentialProperties
```

This command creates a credential object and uses **New-NetworkControllerCredential** to add it to the network controller.

To get the Properties, put the output of **New-NetworkControllerCredential** in a variable (for example, x) and execute x.properties in the Powershell prompt.

## PARAMETERS

### -CertificateThumbprint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.
This is the certificate thumbprint of the certificate.
This thumbprint must also be provided in the *ClientCertificateThumbprint* parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

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

### -ConnectionUri
Specifies the Uniform Resource Identifier (URI) of the Network Controller, used by all Representational State Transfer (REST) clients to connect to the Network Controller.

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
The default is the current user.
This user must be present in the security group provided in the *ClientSecurityGroup* parameter in the **Install-NetworkController** cmdlet or the **Set-NetworkController** cmdlet.

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

### -Etag
Specifies the entity tag (ETag) of the resource.
An ETag is an HTTP response header returned by an HTTP-compliant web server.
An ETag is used to determine change in the content of a resource at a given URL.
The value of the header is an opaque string representing the state of the resource at the time the response was generated.

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

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassInnerException
This thumbprint must also be provided in the *ClientCertificateThumbprint* parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

The thumbprint must be provided only if the network controller client authentication is X509 certificates.
**Get-NetworkController** retrieves that client authentication and authorization information.

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

### -Properties
This contains details about the Credential resource, such as the type of credential (can be username and password, SNMP community string or certificate), the user name of the resource (only applicable if the type is username and password) and the value of the credential.

```yaml
Type: CredentialProperties
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
This is the ID of the credential that will be created or modified.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceMetadata
This parameter contains metadata information for the client, such as the tenant ID, group ID, and resource name.

```yaml
Type: ResourceMetadata
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tags
This thumbprint must also be provided in the *ClientCertificateThumbprint* parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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

### Microsoft.Windows.NetworkController.CredentialProperties

## OUTPUTS

### System.Object

This cmdlet outputs the following information:
- Resource reference URI
- Created time of the resource
- Instance ID of the resource
- Resource Metadata
- Resource ID
- Properties of the resource

## NOTES

## RELATED LINKS

[Get-NetworkControllerCredential](./Get-NetworkControllerCredential.md)

[Install-NetworkController](./Install-NetworkController.md)

[Remove-NetworkControllerCredential](./Remove-NetworkControllerCredential.md)

[Set-NetworkController](./Set-NetworkController.md)

