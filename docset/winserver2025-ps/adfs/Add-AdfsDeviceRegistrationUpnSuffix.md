---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/add-adfsdeviceregistrationupnsuffix?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-AdfsDeviceRegistrationUpnSuffix
---

# Add-AdfsDeviceRegistrationUpnSuffix

## SYNOPSIS
Adds a custom UPN suffix.

## SYNTAX

```
Add-AdfsDeviceRegistrationUpnSuffix [-UpnSuffix] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AdfsDeviceRegistrationUpnSuffix** cmdlet adds a custom user principal name (UPN) suffix that you can use when you register a device with Active Directory Federation Services (AD FS).

In many environments, additional UPN suffixes for users are added after an Active Directory Federation Services (AD FS) deployment is complete.
Run this cmdlet to support device registration for users of the new UPN suffix.
The cmdlet configures a Secure Sockets Layer (SSL) binding that corresponds to the UPN suffix.
The UPN suffix must have a corresponding registration name in the AD FS SSL certificate, for example `enterpriseregistration`.upn suffix.
You can use a wild-card SSL certificate that covers all possible registration names.

## EXAMPLES

### Example 1: Add a UPN suffix for registering a device
```
PS C:\> Add-AdfsDeviceRegistrationUpnSuffix -UpnSuffix "Northamerica.Contoso.com"
```

This command adds the UPN suffix Northamerica.Contoso.com to the list of suffixes that AD FS responds to for device registration requests after the initial deployment of the device registration service.

## PARAMETERS

### -UpnSuffix
Specifies a UPN suffix.
The cmdlet adds and configures the UPN suffix that you specify as a valid registration UPN suffix.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

String objects are received by the *UpnSuffix* parameter.

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AdfsDeviceRegistrationUpnSuffix](./Get-AdfsDeviceRegistrationUpnSuffix.md)

[Remove-AdfsDeviceRegistrationUpnSuffix](./Remove-AdfsDeviceRegistrationUpnSuffix.md)

[Set-AdfsDeviceRegistrationUpnSuffix](./Set-AdfsDeviceRegistrationUpnSuffix.md)

