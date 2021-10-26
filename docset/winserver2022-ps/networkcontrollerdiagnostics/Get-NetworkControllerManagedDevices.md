---
description: The Get-NetworkControllerManagedDevices cmdlet gets managed devices for a Network Controller.
external help file: Debug-NetworkController.psm1-help.xml
Module Name: NetworkControllerDiagnostics
ms.date: 10/22/2021
online version: https://docs.microsoft.com/powershell/module/networkcontrollerdiagnostics/get-networkcontrollermanageddevices?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetworkControllerManagedDevices
---

# Get-NetworkControllerManagedDevices

## SYNOPSIS
Gets managed devices for a Network Controller.

## SYNTAX

```
Get-NetworkControllerManagedDevices [-RestURI] <String> [[-Credential] <PSCredential>]
 [[-CertificateThumbprint] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkControllerManagedDevices** cmdlet gets managed devices for a Network Controller.

## EXAMPLES

### Example 1: Get managed devices
```powershell
Get-NetworkControllerManagedDevices -RestURI  "NC-0.contoso.cloud.com" 
```

This command gets managed devices for the specified Network Controller REST APIs.

## PARAMETERS

### -CertificateThumbprint
Certificate thumbprint to use for Network Controller.
Specify in case of certificate deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Credential to use for Network Controller.
Specify in case of Kerberos deployment.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestURI
The URI to be used for Network Controller REST APIs.
Specify in case of wild card certificate deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[Debug-NetworkControllerConfigurationState](Debug-NetworkControllerConfigurationState.md)

[Debug-ServiceFabricNodeStatus](Debug-ServiceFabricNodeStatus.md)

[Get-NetworkControllerDeploymentInfo](Get-NetworkControllerDeploymentInfo.md)
