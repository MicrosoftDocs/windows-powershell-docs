---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: ADFS
ms.assetid: 7ED241AD-D285-493E-AF6B-F529D8E8F577
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AdfsDeviceRegistration
ms.reviewer:
---

# Get-AdfsDeviceRegistration

## SYNOPSIS
Gets the administrative polices of the Device Registration Service.

## SYNTAX

```
Get-AdfsDeviceRegistration [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsDeviceRegistration** cmdlet gets the administrative polices that are used by the Device Registration Service in Active Directory Federation Services (AD FS).

## EXAMPLES

### Example 1: Get settings of the Device Registration Service
```
PS C:\> Get-AdfsDeviceRegistration


DrsObjectDN          : CN=DeviceRegistrationService,CN=Device Registration Services,CN=Device Registration Configuration,CN=Services,CN=Configuration,DC=contoso,DC=com
DevicesPerUser       : 10
MaximumInactiveDays  : 90
IsEnabledOnPremises  : True
IsEnabledInCloud     : False
DeviceObjectLocation : CN=RegisteredDevices,DC=contoso,DC=com
```

This command gets the current settings for the Device Registration Service in AD FS.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### DeviceRegistrationServiceObject
This cmdlet generates a **DeviceRegistrationServiceObject** object that represents the Device Registration Service.
The object includes the following properties:

- DevicesPerUser Type: **Int**
- MaximumInactiveDays Type: **Int**
- IsEnabledOnPremises: Type: **bool**
- IsEnabledInCloud: Type: **bool**
- DeviceObjectLocation: Type: **string**
- DrsObjectDN: Type: **string**

## NOTES

## RELATED LINKS

[Disable-AdfsDeviceRegistration](./Disable-AdfsDeviceRegistration.md)

[Enable-AdfsDeviceRegistration](./Enable-AdfsDeviceRegistration.md)

[Set-AdfsDeviceRegistration](./Set-AdfsDeviceRegistration.md)

