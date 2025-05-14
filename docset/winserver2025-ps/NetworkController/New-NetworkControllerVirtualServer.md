---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/new-networkcontrollervirtualserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetworkControllerVirtualServer
---

# New-NetworkControllerVirtualServer

## SYNOPSIS

Adds a new virtual server to the Network Controller.
If already present, updates the properties of the virtual server

## SYNTAX

```
New-NetworkControllerVirtualServer [-ResourceId] <String> [-MarkServerReadOnly] <Boolean> [[-Tags] <PSObject>]
 [-Properties] <VirtualServerProperties> [[-Etag] <String>] [[-ResourceMetadata] <ResourceMetadata>] [-Force]
 -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Adds a new virtual server to the Network Controller.
If already present, updates the properties of the virtual server

## EXAMPLES

### Example 1
```
$credentialProperties = [Microsoft.Windows.NetworkController.CredentialProperties]@{Type="UsernamePassword";UserName="admin";Value="password"}
New-NetworkControllerCredential -ResourceId cred1 -ConnectionUri https://restserver -Properties $credentialProperties
$credential= Get-NetworkControllerCredential -ResourceId cred1 -ConnectionUri https://restserver

$virtualserverproperties=New-Object Microsoft.Windows.NetworkController.VirtualServerProperties
$virtualserverproperties.Connections = @([Microsoft.Windows.NetworkController.Connection]@{ManagementAddresses=@("192.168.0.12");Credential=$credential})
$virtualserverproperties.VMGuid="a85b4174-1547-4d55-ad5b-aa309f450d2f"
New-NetworkControllerVirtualServer -ConnectionUri https://restserver -ResourceId VirtualServer1 -Properties $virtualserverproperties
```

Description



The above cmdlet adds a virtual server with name VirtualServer1 to the Network Controller

## PARAMETERS

### -CertificateThumbPrint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.
This is the certificate thumbprint of the certificate.
This thumbprint must also be provided in the ClientCertificateThumbprint parameter in the Install-NetworkController or Set-NetworkController cmdlet so that Network Controller can authorize this user.

```yaml
Type: string
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
The default value is the current user.This user must be present in the security group provided in the ClientSecurityGroup parameter in the Install-NetworkController cmdlet.

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
An ETag (entity tag) is an HTTP response header returned by an HTTP-compliant web server used to determine change in the content of a resource at a given URL.
The value of the header is an opaque string representing the state of the resource at the time the response was generated.

```yaml
Type: string
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

### -MarkServerReadOnly
@{Text=}

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Following properties of server can be added/modified:
1.
List of connections that specifies the information needed to connect to the virtual server for the purposes of managing it.
Each connection will have a management address and a credential reference to connect to the virtual server
2.
VM network GUID associated with the virtual server
3.
Virtual server certificate (needs to be populated only when the virtual server uses a self signed certificate)
4.
Physical server where the virtual server is hosted

```yaml
Type: VirtualServerProperties
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Specifies the unique ID of the virtual server

```yaml
Type: string
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
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
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tags
@{Text=}

```yaml
Type: psobject
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Boolean

### Microsoft.Windows.NetworkController.VirtualServerProperties

Following properties of server can be added/modified:
1.
List of connections that specifies the information needed to connect to the virtual server for the purposes of managing it.
Each connection will have a management address and a credential reference to connect to the virtual server
2.
VM network GUID associated with the virtual server
3.
Virtual server certificate (needs to be populated only when the virtual server uses a self signed certificate)
4.
Physical server where the virtual server is hosted

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

