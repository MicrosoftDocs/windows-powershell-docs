---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Deployment.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/initialize-addeviceregistration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Initialize-ADDeviceRegistration
---

# Initialize-ADDeviceRegistration

## SYNOPSIS
Initializes the Device Registration Service configuration in the Active Directory forest.

## SYNTAX

```
Initialize-ADDeviceRegistration -ServiceAccountName <String> [-DeviceLocation <String>]
 [-RegistrationQuota <UInt32>] [-MaximumRegistrationInactivityPeriod <UInt32>] [-Credential <PSCredential>]
 [-Force] [-DiscoveryName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Initialize-ADDeviceRegistration** cmdlet initializes the Device Registration Service configuration in the Active Directory forest.
To run this cmdlet, you must be logged in with enterprise administrator permissions and your Active Directory forest must have the Windows Server 2012 R2 schema.
To join devices to a workplace, you must run the **Enable-AdfsDeviceRegistration** cmdlet on each Active Directory Federation Services (AD FS) server after this cmdlet has been run successfully.

## EXAMPLES

### Example 1: Initialize the Device Registration Service
```
PS C:\> Initialize-ADDeviceRegistration -ServiceAccountName "CONTOSO\svc_adfs" -DeviceLocation "Contoso.com" -RegistrationQuota 10 -MaximumRegistrationInactivityPeriod 90 -Credential ContosoAdmin
```

This command initializes the Device Registration Service in the Active Directory forest.

## PARAMETERS

### -Credential
Specifies a **PSCredential** object based on a user name and password.
This account must be a member of the Enterprise Admins group.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.

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

### -DeviceLocation
Specifies the domain in which to store the device objects.
Specify a domain in the current forest.

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

### -DiscoveryName
Specifies a discovery name.

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

### -Force
Forces the command to run without asking for user confirmation.

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

### -MaximumRegistrationInactivityPeriod
Specifies the maximum number of days to elapse before a device object is deleted due to inactivity.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RegistrationQuota
Specifies the maximum number of devices that an individual user can register.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceAccountName
Specifies the account to which to grant read and write access to the Device Registration service configuration and containers in Active Directory.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-AdfsDeviceRegistration](./Enable-AdfsDeviceRegistration.md)

