---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Deployment.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/enable-adfsdeviceregistration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-AdfsDeviceRegistration
---

# Enable-AdfsDeviceRegistration

## SYNOPSIS
This cmdlet has been deprecated.

## SYNTAX

```
Enable-AdfsDeviceRegistration [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet has been deprecated for AD FS 2016.
For more information, see [Configure On-Premises Conditional Access using registered devices](/windows-server/identity/ad-fs/operations/configure-device-based-conditional-access-on-premises).

The **Enable-AdfsDeviceRegistration** cmdlet configures a server in an Active Directory Federation Services (AD FS) farm to host the Device Registration Service.
To completely enable the Device Registration Service, you must run this command on each AD FS server in your AD FS farm.
You must run the **Initialize-ADDeviceRegistration** cmdlet before you run this cmdlet.

## EXAMPLES

### Example 1: Enable the device registration service
```
PS C:\> Enable-AdfsDeviceRegistration
Message                                                     Context                                                                                                          Status
-------                                                     -------                                                                                                          ------
The configuration completed successfully.                   DeploymentSucceeded                                                                                             Success
```

This command enables the Device Registration Service on the AD FS server.
Note that you must perform this action on every AD FS server in the farm.

## PARAMETERS

### -Credential
Specifies a **PSCredential** object.

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

[Disable-AdfsDeviceRegistration](./Disable-AdfsDeviceRegistration.md)

[Get-AdfsDeviceRegistration](./Get-AdfsDeviceRegistration.md)

[Initialize-ADDeviceRegistration](./Initialize-ADDeviceRegistration.md)

[Set-AdfsDeviceRegistration](./Set-AdfsDeviceRegistration.md)
