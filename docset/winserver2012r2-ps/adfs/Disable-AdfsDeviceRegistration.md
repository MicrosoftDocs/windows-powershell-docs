---
external help file: Microsoft.IdentityServer.Deployment.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Disable-AdfsDeviceRegistration
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 64A40824-4DCD-4DF8-8EFC-0CE756ACE8C8
---

# Disable-AdfsDeviceRegistration

## SYNOPSIS
Marks the Device Registration Service as disabled on an AD FS server.

## SYNTAX

```
Disable-AdfsDeviceRegistration [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-AdfsDeviceRegistration** cmdlet marks the Device Registration Service as disabled on an Active Directory Federation Services (AD FS) server.
To completely disable the Device Registration Service, you must run this command on each AD FS server in your AD FS farm.

## EXAMPLES

### Example 1: Disable Windows Server Device Registration Service
```
PS C:\> Disable-AdfsDeviceRegistration
```

This command marks the Device Registration Service as disabled on the Active Directory Federation Services (AD FS) server.

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

[Get-AdfsDeviceRegistration](./Get-AdfsDeviceRegistration.md)

[Enable-AdfsDeviceRegistration](./Enable-AdfsDeviceRegistration.md)

[Set-AdfsDeviceRegistration](./Set-AdfsDeviceRegistration.md)

