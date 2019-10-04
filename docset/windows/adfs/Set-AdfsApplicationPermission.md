---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: ADFS
ms.assetid: 01654BC2-6F9D-4539-8200-B3C3DEF46C81
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-AdfsApplicationPermission
ms.reviewer:
---

# Set-AdfsApplicationPermission

## SYNOPSIS
Modifies application permissions.

## SYNTAX

### Identifier (Default)
```
Set-AdfsApplicationPermission [-TargetIdentifier] <String> [-ScopeNames <String[]>] [-Description <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierAddScope
```
Set-AdfsApplicationPermission [-TargetIdentifier] <String> -AddScope <String[]> [-Description <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierRemoveScope
```
Set-AdfsApplicationPermission [-TargetIdentifier] <String> -RemoveScope <String[]> [-Description <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Set-AdfsApplicationPermission [-InputObject] <OAuthPermission> [-ScopeNames <String[]>] [-Description <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObjectAddScope
```
Set-AdfsApplicationPermission [-InputObject] <OAuthPermission> -AddScope <String[]> [-Description <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObjectRemoveScope
```
Set-AdfsApplicationPermission [-InputObject] <OAuthPermission> -RemoveScope <String[]> [-Description <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RoleIdentifier
```
Set-AdfsApplicationPermission [[-TargetClientRoleIdentifier] <String>] [[-TargetServerRoleIdentifier] <String>]
 [-ScopeNames <String[]>] [-Description <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RoleIdentifierAddScope
```
Set-AdfsApplicationPermission [[-TargetClientRoleIdentifier] <String>] [[-TargetServerRoleIdentifier] <String>]
 -AddScope <String[]> [-Description <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RoleIdentifierRemoveScope
```
Set-AdfsApplicationPermission [[-TargetClientRoleIdentifier] <String>] [[-TargetServerRoleIdentifier] <String>]
 -RemoveScope <String[]> [-Description <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsApplicationPermission** cmdlet modifies application permissions.

## EXAMPLES

## PARAMETERS

### -AddScope
```yaml
Type: String[]
Parameter Sets: IdentifierAddScope, InputObjectAddScope, RoleIdentifierAddScope
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description
Specifies a description.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies an **OAuthPermission** object.

```yaml
Type: OAuthPermission
Parameter Sets: InputObject, InputObjectAddScope, InputObjectRemoveScope
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RemoveScope
```yaml
Type: String[]
Parameter Sets: IdentifierRemoveScope, InputObjectRemoveScope, RoleIdentifierRemoveScope
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScopeNames
```yaml
Type: String[]
Parameter Sets: Identifier, InputObject, RoleIdentifier
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetClientRoleIdentifier
```yaml
Type: String
Parameter Sets: RoleIdentifier, RoleIdentifierAddScope, RoleIdentifierRemoveScope
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetIdentifier
Specifies the identifier of the target.

```yaml
Type: String
Parameter Sets: Identifier, IdentifierAddScope, IdentifierRemoveScope
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetServerRoleIdentifier
Specifies the identifier of the target server role.

```yaml
Type: String
Parameter Sets: RoleIdentifier, RoleIdentifierAddScope, RoleIdentifierRemoveScope
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Get-AdfsApplicationPermission](./Get-AdfsApplicationPermission.md)

[Grant-AdfsApplicationPermission](./Grant-AdfsApplicationPermission.md)

[Revoke-AdfsApplicationPermission](./Revoke-AdfsApplicationPermission.md)

