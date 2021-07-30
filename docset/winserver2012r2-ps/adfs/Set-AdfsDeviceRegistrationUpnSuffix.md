---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/adfs/set-adfsdeviceregistrationupnsuffix?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsDeviceRegistrationUpnSuffix
---

# Set-AdfsDeviceRegistrationUpnSuffix

## SYNOPSIS
Sets the list of UPN suffixes.

## SYNTAX

```
Set-AdfsDeviceRegistrationUpnSuffix [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsDeviceRegistrationUpnSuffix** cmdlet sets the list of user principal name (UPN) suffixes that you can use when you register a device with Active Directory Federation Services (AD FS).
The cmdlet discovers the UPN suffixes that are in use in the organization and configures the Secure Sockets Layer (SSL) bindings that correspond to the UPN suffix.
Any discovered UPN suffix must have a corresponding registration name in the SSL certificate for AD FS; for example, `enterpriseregistration.`upn suffix.
You can also use a wildcard SSL certificate that covers all possible registration names.
This cmdlet does not affect the custom UPN suffixes that you set manually by running the Add-AdfsDeviceRegistrationUpnSuffix cmdlet.

## EXAMPLES

### Example 1: Set the list of UPN suffixes
```
PS C:\> Set-AdfsDeviceRegistrationUpnSuffix
```

This command sets the list of UPN suffixes that you can use when you register a device.

### Example 2: Set the list of UPN suffixes without confirming
```
PS C:\> Set-AdfsDeviceRegistrationUpnSuffix -Force
```

This command sets the list of UPN suffixes without prompting you for confirmation.

## PARAMETERS

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

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByValue)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### switch

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AdfsDeviceRegistrationUpnSuffix](./Get-AdfsDeviceRegistrationUpnSuffix.md)

[Add-AdfsDeviceRegistrationUpnSuffix](./Add-AdfsDeviceRegistrationUpnSuffix.md)

[Remove-AdfsDeviceRegistrationUpnSuffix](./Remove-AdfsDeviceRegistrationUpnSuffix.md)

