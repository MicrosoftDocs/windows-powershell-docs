---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/revoke-adfsapplicationpermission?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Revoke-AdfsApplicationPermission
---

# Revoke-AdfsApplicationPermission

## SYNOPSIS
Revokes permission for an application.

## SYNTAX

### Identifier (Default)
```
Revoke-AdfsApplicationPermission [-TargetIdentifier] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RoleIdentifier
```
Revoke-AdfsApplicationPermission [[-TargetClientRoleIdentifier] <String>]
 [[-TargetServerRoleIdentifier] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Revoke-AdfsApplicationPermission [-InputObject] <OAuthPermission> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Revoke-AdfsApplicationPermission** cmdlet revokes permission for an application in Active Directory Federation Services (AD FS).

## EXAMPLES

## PARAMETERS

### -InputObject
Specifies an **OAuthPermission** object.

```yaml
Type: OAuthPermission
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetClientRoleIdentifier
```yaml
Type: String
Parameter Sets: RoleIdentifier
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -TargetIdentifier
```yaml
Type: String
Parameter Sets: Identifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetServerRoleIdentifier
```yaml
Type: String
Parameter Sets: RoleIdentifier
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### Microsoft.IdentityServer.Management.Resources.OAuthPermission

OAuthPermission objects are received by the *InputObject* parameter.

### System.String

String objects are received by the *TargetClientRoleIdentifier*, *TargetIdentifier*, and *TargetServerRoleIdentifier* parameters.

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AdfsApplicationPermission](./Get-AdfsApplicationPermission.md)

[Grant-AdfsApplicationPermission](./Grant-AdfsApplicationPermission.md)

[Set-AdfsApplicationPermission](./Set-AdfsApplicationPermission.md)

