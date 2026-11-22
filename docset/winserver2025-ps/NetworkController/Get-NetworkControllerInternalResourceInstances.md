---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollerinternalresourceinstances?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerInternalResourceInstances
---

# Get-NetworkControllerInternalResourceInstances

## SYNOPSIS
Returns the mapping for instances IDs to REST resource IDs.

## SYNTAX

```
Get-NetworkControllerInternalResourceInstances [[-ResourceId] <String[]>] -ConnectionUri <Uri>
 [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerInternalResourceInstances** cmdlet returns the mapping for instances IDs, which are GUIDs, to REST resource IDs, which are names. It is a reverse lookup mechanism.


## EXAMPLES

### Example 1

This example shows all the resources in the Network Controller with their corresponding instance IDs. The "Properties" field has the actual reference of the resource and the provisioning state.

```
Get-NetworkControllerInternalResourceInstances -ConnectionUri https://networkcontroller
```

## PARAMETERS

### -CertificateThumbprint

Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.This is the certificate thumbprint of the certificate.This thumbprint must also be provided in the *ClientCertificateThumbprint* parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

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

Specifies a user credential that has permission to perform this action.The default value is the current user.This user must be present in the security group provided in the *ClientSecurityGroup* parameter in the **Install-NetworkController** cmdlet.

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

Passes an inner exception.

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

Specifies an array of one or more resources to retrieve. If ResourceID is not provided, all the resources in the Network Controller will be retrieved.

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

The resource has the following output:
1. Resource ID
2. Instance ID of the resource
3. Actual reference of the resource
4. Provisioning state of the resource

## NOTES

## RELATED LINKS

