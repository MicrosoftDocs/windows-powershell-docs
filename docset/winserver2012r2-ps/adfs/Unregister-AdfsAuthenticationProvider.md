---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Unregister-AdfsAuthenticationProvider
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
ms.assetid: 38DA24A1-6AF2-4E4A-80D1-7D15DFEE871A
---

# Unregister-AdfsAuthenticationProvider

## SYNOPSIS
Deletes an external authentication provider from AD FS.

## SYNTAX

```
Unregister-AdfsAuthenticationProvider [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Unregister-AdfsAuthenticationProvider** cmdlet deletes an external authentication provider from Active Directory Federation Services (AD FS).
Use the Get-AdfsAuthenticationProvider cmdlet to get a list of registered authentication providers.

## EXAMPLES

### Example 1: Delete a registered authentication provider
```
PS C:\> Unregister-AdfsAuthenticationProvider -Name "ContosoExternalAuthProvider"
```

This command deletes the additional authentication provider named ContosoExternalAuthProvider.

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

### -Name
Specifies the name of an authentication provider to delete from AD FS.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

### System.Object

## NOTES

## RELATED LINKS

[Get-AdfsAuthenticationProvider](./Get-AdfsAuthenticationProvider.md)

[Register-AdfsAuthenticationProvider](./Register-AdfsAuthenticationProvider.md)

