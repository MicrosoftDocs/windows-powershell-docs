---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: ADFS
ms.assetid: 6DA91F9C-EB04-440A-83EA-382F6DA2CF07
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Remove-AdfsDeviceRegistrationUpnSuffix
ms.reviewer:
---

# Remove-AdfsDeviceRegistrationUpnSuffix

## SYNOPSIS
Removes a custom UPN suffix.

## SYNTAX

```
Remove-AdfsDeviceRegistrationUpnSuffix [-UpnSuffix] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AdfsDeviceRegistrationUpnSuffix** cmdlet removes a custom user principal name (UPN) suffix.
The cmdlet removes the UPN suffix and the SSL binding that corresponds to the UPN suffix.
After you remove a custom UPN suffix, accounts that have a UPN that corresponds to the specified UPN suffix can no longer register devices.
Use the **Add-AdfsDeviceRegistrationUpnSuffix** cmdlet to add a custom UPN suffix.

## EXAMPLES

### Example 1: Remove a custom UPN suffix
```
PS C:\> Remove-AdfsDeviceRegistrationUpnSuffix -UpnSuffix "Child.Contoso.com" -Force
```

This command removes the UPN suffix Child.Contoso.com from the list of acceptable UPN suffixes for users to workplace join their devices.

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
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpnSuffix
Specifies a UPN suffix.
The cmdlet removes the UPN suffix that you specify as a valid registration UPN suffix.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### string

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AdfsDeviceRegistrationUpnSuffix](./Add-AdfsDeviceRegistrationUpnSuffix.md)

[Get-AdfsDeviceRegistrationUpnSuffix](./Get-AdfsDeviceRegistrationUpnSuffix.md)

[Set-AdfsDeviceRegistrationUpnSuffix](./Set-AdfsDeviceRegistrationUpnSuffix.md)

