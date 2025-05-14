---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/get-adfsdeviceregistrationupnsuffix?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsDeviceRegistrationUpnSuffix
---

# Get-AdfsDeviceRegistrationUpnSuffix

## SYNOPSIS
Gets the UPN suffixes that can be used with device registration.

## SYNTAX

```
Get-AdfsDeviceRegistrationUpnSuffix [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsDeviceRegistrationUpnSuffix** cmdlet gets all of the user principal name (UPN) suffixes that you can use when you register a device with Active Directory Federation Services (AD FS).
The cmdlet returns a list of UPN suffixes and indicates whether a UPN suffix was discovered or manually configured by the administrator, and if the server has a valid SSL binding configured for the UPN suffix.

## EXAMPLES

### Example 1: Get the UPN suffixes for the device registration service
```
PS C:\> Get-AdfsDeviceRegistrationUpnSuffix | Format-List
Upn               : contoso.com
SslPort           : 443
IsSetAsSslBinding : True
IsCustom          : False
```

This command gets information on the UPN suffixes that are accepted by the Device Registration Service in AD FS.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.IdentityServer.Management.Commands.GetAdfsDeviceRegistrationUpnSuffix+DrsBinding

Returns one or more DrsBinding objects that represent the device registration service UPN suffix resources for the Federation Service.

## NOTES

## RELATED LINKS

[Add-AdfsDeviceRegistrationUpnSuffix](./Add-AdfsDeviceRegistrationUpnSuffix.md)

[Remove-AdfsDeviceRegistrationUpnSuffix](./Remove-AdfsDeviceRegistrationUpnSuffix.md)

[Set-AdfsDeviceRegistrationUpnSuffix](./Set-AdfsDeviceRegistrationUpnSuffix.md)
