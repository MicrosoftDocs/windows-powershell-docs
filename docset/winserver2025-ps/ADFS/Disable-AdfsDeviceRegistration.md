---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Deployment.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/disable-adfsdeviceregistration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-AdfsDeviceRegistration
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-AdfsDeviceRegistration](./Enable-AdfsDeviceRegistration.md)

[Get-AdfsDeviceRegistration](./Get-AdfsDeviceRegistration.md)

[Set-AdfsDeviceRegistration](./Set-AdfsDeviceRegistration.md)

