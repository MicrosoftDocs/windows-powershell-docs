---
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
online version: https://learn.microsoft.com/powershell/module/networkcontroller/set-networkcontrollermultisiteprimary?view=windowsserver2025-ps
schema: 2.0.0
---

# Set-NetworkControllerMultisitePrimary

## SYNOPSIS

Sets the primary site of a NetworkController Site.

## SYNTAX

```
Set-NetworkControllerMultisitePrimary [[-Tags] <PSObject>] [-Properties]
<NetworkControllerMultisitePrimaryProperties> [[-Etag] <String>] [[-ResourceMetadata]
<ResourceMetadata>] [[-ResourceId] <String>] [-Force] -ConnectionUri <Uri>
[-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException] [-WhatIf]
[-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Set-NetworkControllerMultisitePrimary` cmdlet is used to change the primary site of a
location in a Multisite configuration. This can be done in the off-chance that your original
Primary site has gone offline and policies still need to be pushed and applied. Note, any
policies that were being configured at the moment when the original primary site crashes will be
lost and must be redone.

## EXAMPLES

### Example 1: Set new Primary site 

```powershell
$prop = new-object
Microsoft.Windows.NetworkController.NetworkControllerMultisitePrimaryProperties 

Set-NetworkControllerMultisitePrimary -ConnectionUri 'https://site1.com' -Properties $prop
-Force
```

## PARAMETERS

### -CertificateThumbprint

Specifies the digital public key X.509 certificate of a user account that has permission to
perform this action. Specify this parameter only if you run this cmdlet on a computer that is
not part of the network controller cluster.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionUri

Specifies the Uniform Resource Identifier (URI) of a Network Controller. 

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies a user credential that has permission to perform this action. The default is the
current user. Specify this parameter only if you run this cmdlet on a computer that is not part
of the network controller cluster.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Etag

Specifies the entity tag (ETag) parameter of the resource. An ETag (entity tag) is an HTTP
response header returned by an HTTP-compliant web server used to determine change in the content
of a resource at a given URL. The value of the header is an opaque string representing the state
of the resource at the time the response was generated.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Forces the command to run without asking for user confirmation

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassInnerException

This thumbprint must also be provided in the **ClientCertificateThumbprint** parameter in the
`Install-NetworkController` or `Set-NetworkController` cmdlet so that Network Controller can
authorize this user. The thumbprint must be provided only if the network controller client
authentication is X509 certificates. `Get-NetworkController` retrieves that client authentication
and authorization information.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Properties

Specifies the primary site of a location.

```yaml
Type: Microsoft.Windows.NetworkController.NetworkControllerMultisitePrimaryProperties
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId

Specifies the unique identifier for the Multisite configuration

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceMetadata

This parameter contains metadata information for the client.

```yaml
Type: Microsoft.Windows.NetworkController.ResourceMetadata
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tags

@{Text=}

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
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
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.NetworkController.NetworkControllerMultisitePrimaryProperties

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Set-NetworkControllerMultisiteConfiguration](./Set-NetworkControllerMultisiteConfiguration.md)

[Get-NetworkControllerMultisiteConfiguration](./Get-NetworkControllerMultisiteConfiguration.md)

