---
external help file: Microsoft.IdentityServer.Deployment.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Enable-AdfsDeviceRegistration
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: CCFC562A-AF1E-488E-B85D-1F12A6D8C9C5
---

# Enable-AdfsDeviceRegistration

## SYNOPSIS
Configures a server in an AD FS farm to host the Device Registration Service.

## SYNTAX

```
Enable-AdfsDeviceRegistration [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-AdfsDeviceRegistration** cmdlet configures a server in an Active Directory Federation Services (AD FS) farm to host the Device Registration Service.
To completely enable the Device Registration Service, you must run this command on each AD FS server in your AD FS farm.
You must run the Initialize-ADDeviceRegistration cmdlet before you run this cmdlet.

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

### -Credential
Specifies a **PSCredential** object based on a user name and password for the Active Directory account under which the AD FS service runs.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936)

[Get-AdfsDeviceRegistration](./Get-AdfsDeviceRegistration.md)

[Disable-AdfsDeviceRegistration](./Disable-AdfsDeviceRegistration.md)

[Set-AdfsDeviceRegistration](./Set-AdfsDeviceRegistration.md)

[Initialize-ADDeviceRegistration](./Initialize-ADDeviceRegistration.md)

