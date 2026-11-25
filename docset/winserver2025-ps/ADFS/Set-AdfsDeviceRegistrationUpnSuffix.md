---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsdeviceregistrationupnsuffix?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
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
This cmdlet does not affect the custom UPN suffixes that you set manually by running the **Add-AdfsDeviceRegistrationUpnSuffix** cmdlet.

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

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### System.Management.Automation.SwitchParameter

SwitchParameter objects are received by the *Force* parameter.

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AdfsDeviceRegistrationUpnSuffix](./Add-AdfsDeviceRegistrationUpnSuffix.md)

[Get-AdfsDeviceRegistrationUpnSuffix](./Get-AdfsDeviceRegistrationUpnSuffix.md)

[Remove-AdfsDeviceRegistrationUpnSuffix](./Remove-AdfsDeviceRegistrationUpnSuffix.md)

