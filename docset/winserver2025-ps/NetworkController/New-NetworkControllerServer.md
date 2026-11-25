---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/new-networkcontrollerserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetworkControllerServer
---

# New-NetworkControllerServer

## SYNOPSIS
Creates or Updates a server resource in the Network Controller

## SYNTAX

```
New-NetworkControllerServer [-ResourceId] <String> [[-Tags] <PSObject>] [-Properties] <ServerProperties>
 [[-Etag] <String>] [[-ResourceMetadata] <ResourceMetadata>] [-Force] -ConnectionUri <Uri>
 [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-NetworkControllerServer** cmdlet creates updates a physical server resource in the Network Controller, or updates an existing one.
After you add the server resource, Network Controller manages that server.

## EXAMPLES

### Example 1: Add a server
```
PS C:\> $CredentialProperties = [Microsoft.Windows.NetworkController.CredentialProperties]@{Type="UsernamePassword";UserName="admin";Value="password"}
PS C:\> New-NetworkControllerCredential -ResourceId "Credential01" -ConnectionUri "https://restserver" -Properties $CredentialProperties
PS C:\> $Credential = Get-NetworkControllerCredential -ResourceId "Credential01" -ConnectionUri "https://restserver"
PS C:\> $ServerProperties = New-Object Microsoft.Windows.NetworkController.ServerProperties
PS C:\> $ServerProperties.Connections = @([Microsoft.Windows.NetworkController.Connection]@{ManagementAddresses=@("192.168.0.12");Credential=$Credential})
PS C:\> $ServerProperties.RackSlot = "1"
PS C:\> $ServerProperties.OS = "Windows Server 2016"
PS C:\> $ServerProperties.Vendor = "Dell"
PS C:\> $ServerProperties.Model = "PowerEdge R730"
PS C:\> New-NetworkControllerServer -ConnectionUri "https://networkcontroller" -ResourceId "Server01" -Properties $ServerProperties
```

The first command creates a **CredentialProperties** object, and then stores it in the $CredentialProperties variable.

The second command creates a credential that has the properties in $CredentialProperties by using the **New-NetworkControllerCredential** cmdlet.

The third command gets the credential by using the **Get-NetworkControllerCredential** cmdlet, and then stores it in the $Credential variable.

The fourth command creates a **ServerProperties** object by using the **New-Object** cmdlet.
The command stores the object in the $ServerProperties variable.

The next five commands assign values to properties of $ServerProperties.

The final command adds a server to the Network Controller that has the resource ID Server01.
The command identifies the Network Controller by URI.
The command specifies the properties of the server by using $ServerProperties.

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

### -Etag
Specifies the entity tag (ETag) parameter of the resource.
An ETag is an HTTP response header returned by an HTTP-compliant web server.
An ETag is used to determine change in the content of a resource.
The value of the header is an opaque string that represents the state of the resource when the response was generated.

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
This thumbprint must also be provided in the **ClientCertificateThumbprint** parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

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
Specifies the properties of a server that this cmdlet creates or updates.
You can specify the following properties:

- Connections that specifies the information that is required to connect to the server for the purposes of managing it.
Each connection has a management address and a credential reference to connect to the server.
- Model number.
- Array of physical network interfaces on the server.
- Operating system that runs on the server.
- Slot in the rack in which the server is connected.
- Serial number.
- Server vendor name.

```yaml
Type: ServerProperties
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Specifies the resource ID of the server that this cmdlet creates or modifies.

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
Specifies the resource ID of the server interface that this cmdlet adds or updates.

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

### Microsoft.Windows.NetworkController.ServerProperties

You can pipe an object to this cmdlet that contains the following properties:

- Connections that specifies the information that is required to connect to the server for the purposes of managing it.
Each connection has a management address and a credential reference to connect to the server.
- Model number.
- Array of physical network interfaces on the server.
- Operating system that runs on the server.
- Slot in the rack in which the server is connected.
- Serial number.
- Server vendor name.

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-NetworkControllerCredential](./Get-NetworkControllerCredential.md)

[Get-NetworkControllerServer](./Get-NetworkControllerServer.md)

[Install-NetworkController](./Install-NetworkController.md)

[New-NetworkControllerCredential](./New-NetworkControllerCredential.md)

[Remove-NetworkControllerServer](./Remove-NetworkControllerServer.md)

[Set-NetworkController](./Set-NetworkController.md)

