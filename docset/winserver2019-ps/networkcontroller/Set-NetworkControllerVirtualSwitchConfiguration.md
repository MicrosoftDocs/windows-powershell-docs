---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
manager: jasgro
Module Name: NetworkController
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/networkcontroller/set-networkcontrollervirtualswitchconfiguration?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetworkControllerVirtualSwitchConfiguration
---

# Set-NetworkControllerVirtualSwitchConfiguration

## SYNOPSIS

This cmdlet sets the global settings of the virtual switch from the Network Controller.

## SYNTAX

```
Set-NetworkControllerVirtualSwitchConfiguration -ConnectionUri <Uri>
 -Properties <VirtualSwitchManagerProperties> [-CertificateThumbPrint <string>] [-Credential <PSCredential>]
 [-Etag <string>] [-Force] [-ResourceId <string>] [-ResourceMetadata <ResourceMetadata>] [-Tags <psobject>]
```

## DESCRIPTION
This cmdlet sets the global settings of the virtual switch from the Network Controller.
This primarily sets Quality of Service settings for all virtual switches managed by the Network Controller.

## EXAMPLES

### Example 1
```
$Qos=New-Object Microsoft.Windows.NetworkController.VirtualSwitchQosSettings
$Qos.ReservationMode="Weight"
$vswitchSettings=New-Object Microsoft.Windows.NetworkController.VirtualSwitchManagerProperties
$vswitchSettings.QosSettings=$qos
Set-NetworkControllerVirtualSwitchConfiguration -ConnectionUri https://networkcontroller -Properties $vswitchSettings
```

Description



This example first creates a resource for QoS settings and sets the reservation mode to "Weight".
Then, it sets the virtual switch manager settings with the QoS settings.

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
Following properties can be set for the virtual switch configuration:
1.
Reservation mode for QoS: absolute or Weight
2.
Link speed percentage
3.
Default reservation for QoS
4.
Whether hardware limits are enabled for QoS
5.
Whether hardware reservations are enabled for QoS
6.
Whether software reservations are enabled for QoS

```yaml
Type: VirtualSwitchManagerProperties
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Specifies the identifier for QoS settings.
This is not used.

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
Following properties can be set for the virtual switch configuration:
1.
Reservation mode for QoS: absolute or Weight
2.
Link speed percentage
3.
Default reservation for QoS
4.
Whether hardware limits are enabled for QoS
5.
Whether hardware reservations are enabled for QoS
6.
Whether software reservations are enabled for QoS

## OUTPUTS

## NOTES
## RELATED LINKS

