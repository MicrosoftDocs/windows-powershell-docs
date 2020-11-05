---
external help file: 
Module Name: RemoteDesktop
online version: 
schema: 2.0.0
title: Get-RDLicenseConfiguration
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: E77214D7-17EF-4BA4-B4EE-4CC7E741C4BE
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-RDLicenseConfiguration

## SYNOPSIS
Retrieves the current settings for the RD Licensing server and the licensing mode of the Remote Desktop deployment.

## SYNTAX

```
Get-RDLicenseConfiguration [[-ConnectionBroker] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDLicenseConfiguration** cmdlet retrieves the current settings for the Remote Desktop Licensing (RD Licensing) server and the licensing mode of the Remote Desktop deployment.

RD Licensing servers manage the Remote Desktop Services client access licenses (RDS CALs) that each device or user requires to connect to a Remote Desktop Session Host (RD Session Host) server.

## EXAMPLES

### Example 1: Retrieve the Remote Desktop license configuration
```
PS C:\> Get-RDLicenseConfiguration -ConnectionBroker "Rdcb.Contoso.com"
```

This command retrieves the Remote Desktop license configuration for the RD Connection Broker server named Rdcb.Contoso.com.

## PARAMETERS

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for this Remote Desktop deployment.
If you do not supply a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object
- Mode (string). Remote Desktop licensing mode that you configured for the deployment. Valid values are PerUser and PerDevice.

- LicenseServer (string\[\]). FQDN of the Remote Desktop license server that you configured for the deployment.

## NOTES

## RELATED LINKS

[Set-RDLicenseConfiguration](./Set-RDLicenseConfiguration.md)

