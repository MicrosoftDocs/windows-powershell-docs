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
title: New-NetworkControllerServiceInsertion
ms.reviewer:
ms.assetid: 3D9A62FA-1E11-49AD-9135-5F3738D76E9F
---

# New-NetworkControllerServiceInsertion

## SYNOPSIS

This cmdlet adds a new service insertion resource to the Network Controller

## SYNTAX

```
New-NetworkControllerServiceInsertion -ConnectionUri <Uri> -Properties <ServiceInsertionProperties>
 -ResourceId <string> [-CertificateThumbPrint <string>] [-Credential <PSCredential>] [-Etag <string>] [-Force]
 [-ResourceMetadata <ResourceMetadata>] [-Tags <psobject>]
```

## DESCRIPTION
This cmdlet adds a new service insertion resource to the Network Controller.
This is useful for cases like port mirroring, so that traffic from one VM can be mirrored to another VM, say for inspection purposes.

## EXAMPLES

### Example 1
```
$dstNic = get-networkcontrollernetworkinterface -ConnectionUri https://networkcontroller -ResourceId "Appliance_Ethernet1"

$portmirror = [Microsoft.Windows.NetworkController.ServiceInsertionProperties]::new()
$portMirror.Priority = 1

//Create service insertion rules object to contain rules that must be matched in order for traffic to be sent to appliance
$portmirror.ServiceInsertionRules = [Microsoft.Windows.NetworkController.ServiceInsertionRule[]]::new(1)

$portmirror.ServiceInsertionRules[0] = [Microsoft.Windows.NetworkController.ServiceInsertionRule]::new()
$portmirror.ServiceInsertionRules[0].ResourceId = "Rule1"
$portmirror.ServiceInsertionRules[0].Properties = [Microsoft.Windows.NetworkController.ServiceInsertionRuleProperties]::new()

$portmirror.ServiceInsertionRules[0].Properties.Description = "Port Mirror Rule"
$portmirror.ServiceInsertionRules[0].Properties.Protocol = "All"
$portmirror.ServiceInsertionRules[0].Properties.SourcePortRangeStart = "0"
$portmirr
```

Description



The above example creates a service insertion object that mirrors the traffic to the destination NIC specified by "Appliance_Ethernet1".
This objet can be applied to a network interface so that the traffic from that network interface is mirrored to "Appliance_Enternet1".

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
Type: switch
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Properties
Following properties for service insertion can be added/changed:
a.
For each service insertion rule, the following can be specified
    1.
Description of rule
    2.
Protocol
    3.
Starting source port
    4.
Ending source port
    5.
Starting destination port
    6.
Ending destination port
    7.
Source subnet(s)
    8.
Destination subnet(s)
b.
For each destination element where service insertion has to be applied
    1.
Description
    2.
Destination network interface
    3.
Order of the element

```yaml
Type: ServiceInsertionProperties
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Specifies the ID of the resource to be created

```yaml
Type: string
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

## INPUTS

### 
Following properties for service insertion can be added/changed:
a.
For each service insertion rule, the following can be specified
    1.
Description of rule
    2.
Protocol
    3.
Starting source port
    4.
Ending source port
    5.
Starting destination port
    6.
Ending destination port
    7.
Source subnet(s)
    8.
Destination subnet(s)
b.
For each destination element where service insertion has to be applied
    1.
Description
    2.
Destination network interface
    3.
Order of the element

## OUTPUTS

## NOTES
## RELATED LINKS

