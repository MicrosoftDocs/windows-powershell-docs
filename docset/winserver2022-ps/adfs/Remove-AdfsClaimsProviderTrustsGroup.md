---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
manager: jasgro
Module Name: ADFS
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/adfs/remove-adfsclaimsprovidertrustsgroup?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-AdfsClaimsProviderTrustsGroup
---

# Remove-AdfsClaimsProviderTrustsGroup

## SYNOPSIS
Removes an AD FS claims provider trust group.

## SYNTAX

```
Remove-AdfsClaimsProviderTrustsGroup -TargetIdentifier <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AdfsClaimsProviderTrustsGroup** cmdlet removes an Active Directory Federation Services (AD FS) claims provider trust group.

## EXAMPLES

## PARAMETERS

### -TargetIdentifier
Specifies the ID of the target.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AdfsClaimsProviderTrustsGroup](./Add-AdfsClaimsProviderTrustsGroup.md)

[Get-AdfsClaimsProviderTrustsGroup](./Get-AdfsClaimsProviderTrustsGroup.md)

