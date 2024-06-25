---
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
online version: https://learn.microsoft.com/powershell/module/networkcontroller/set-networkcontrollermultisiteconfiguration?view=windowsserver2025-ps
schema: 2.0.0
---

# Set-NetworkControllerMultisiteConfiguration

## SYNOPSIS

Initiates site peering between NC infrastructures across two different locations.

## SYNTAX

```
Set-NetworkControllerMultisiteConfiguration [[-Tags] <PSObject>] [-Properties]
<NetworkControllerMultisiteProperties> [[-Etag] <String>] [[-ResourceMetadata]
<ResourceMetadata>] [[-ResourceId] <String>] [-Force] -ConnectionUri <Uri>
[-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException] [-WhatIf]
[-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Set-NetworkControllerMultisiteConfiguration` cmdlet initiates a Multisite peering connection
between two NC infrastructures. For instance, if you have site A with NC infrastructure A and
site B with NC infrastructure B, then you can initiate a peer between NC infrastructure A and NC
infrastructure B. This cmdlet can not only initiate peering but can also remove peering and
change the status of a NC infrastructure to primary. Additionally, this cmdlet can also be used
to edit site properties once configured.

## EXAMPLES

### Example 1: Initiate Peering with Self-Signed Certificates

```powershell
$cert1 = Get-ChildItem 'Cert:\LocalMachine\My' | where {$_.Subject -like ‘sdnsite1.contoso.com’}
$base64cert1 = [System.Convert]::ToBase64String($cert1.RawData)
$cert2 = Get-ChildItem “Cert:\LocalMachine\My” | where {$_.Subject -like ‘sdnsite2.contoso.com’}
$base64cert2 = [System.Convert]::ToBase64String($cert2.RawData)

$prop = new-object Microsoft.Windows.NetworkController.NetworkControllerMultisiteProperties
$prop.certificateSubjectName = 'sdnsite1.contoso.com'
$prop.Sites = new-object Microsoft.Windows.NetworkController.NetworkControllerSite
$prop.Sites[0].ResourceId = 'site2'
$prop.Sites[0].Properties = new-object
Microsoft.Windows.NetworkController.NetworkControllerSiteProperties

$prop.Sites[0].Properties.RestIPAddress = 'sdnsite2.contoso.com'
$prop.Sites[0].Properties.CertificateSubjectName = 'sdnsite2.contoso.com'
$prop.Sites[0].Properties.EncodedCertificate = $base64cert2

Set-NetworkControllerMultisiteConfiguration -ConnectionUri 'https://sdnsite1.contoso.com'
-Properties $prop -Force

$prop = new-object Microsoft.Windows.NetworkController.NetworkControllerMultisiteProperties
$prop.certificateSubjectName = 'sdnsite2.contoso.com'
$prop.Sites = new-object Microsoft.Windows.NetworkController.NetworkControllerSite
$prop.Sites[0].ResourceId = 'site1'
$prop.Sites[0].Properties = new-object
Microsoft.Windows.NetworkController.NetworkControllerSiteProperties

$prop.Sites[0].Properties.RestIPAddress = 'sdnsite1.contoso.com'
$prop.Sites[0].Properties.CertificateSubjectName = 'sdnsite1.contoso.com'
$prop.Sites[0].Properties.EncodedCertificate = $base64cert1

Set-NetworkControllerMultisiteConfiguration -ConnectionUri 'https://sdnsite2.contoso.com'
-Properties $prop -Force
```

### Example 2: Removing Peering after Multisite has been set-up

```powershell
$prop = new-object Microsoft.Windows.NetworkController.NetworkControllerMultisiteProperties

Set-NetworkControllerMultisiteConfiguration -ConnectionUri 'https://site1.com' -Properties $prop
-Force

Set-NetworkControllerMultisiteConfiguration -ConnectionUri 'https://site2.com' -Properties $prop
-Force
```

### Example 3: Removing a site where site property is an empty array or has a null value

```powershell
$multisiteProp = new-object
Microsoft.Windows.NetworkController.NetworkControllerMultisiteProperties

Set-NetworkControllerMultisiteConfiguration -ConnectionUri $site2Url -Properties $multisiteProp
-Force
	
Set-NetworkControllerMultisiteConfiguration -ConnectionUri $site1Url -Properties $multisiteProp
-Force
```

### Example 4: **NetworkControllerMultisiteProperties** object properties

- CertificateSubjectName
- [[Sites] \<NetworkControllerSite\>]
    - ResourceID/RESTIPAddress
    - IsPrimary
    - State
    - DeploymentID
    - APIVersion
    - ConfigurationState
    - [[Properties] \<NetworkControllerSiteProperties\>]
        - RestIPAddress
        - CertificateSubjectName
        - EncodedCertificate

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

Specifies a site configuration for Multisite Peering. Site configuration comes as a
NetworkControllerMultisiteProperties object. This object can be defined as new-object
**Microsoft.Windows.NetworkController.NetworkControllerMultisiteProperties**. 

```yaml
Type: Microsoft.Windows.NetworkController.NetworkControllerMultisiteProperties
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

Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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

### Microsoft.Windows.NetworkController.NetworkControllerMultisiteProperties

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-NetworkControllerMultisiteConfiguration](./Get-NetworkControllerMultisiteConfiguration.md)

[Set-NetworkControllerMultisitePrimary](./Set-NetworkControllerMultisitePrimary.md)
