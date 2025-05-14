---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/remove-adfsscopedescription?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-AdfsScopeDescription
---

# Remove-AdfsScopeDescription

## SYNOPSIS
Removes a scope description in AD FS.

## SYNTAX

### Name
```
Remove-AdfsScopeDescription [-TargetName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Remove-AdfsScopeDescription [-InputObject] <OAuthScopeDescription> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AdfsScopeDescription** cmdlet removes a scope description that represents the scope of access granted to resources and applications in Active Directory Federation Services (AD FS).

## EXAMPLES

## PARAMETERS

### -InputObject
Specifies the scope description that this cmdlet removes.

```yaml
Type: OAuthScopeDescription
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetName
Specifies the name of the scope description that this cmdlet removes.

```yaml
Type: String
Parameter Sets: Name
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.IdentityServer.Management.Resources.OAuthScopeDescription

OAuthScopeDescription objects are received by the *InputObject* parameter.

### System.String

String objects are received by the *TargetName* parameter.

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AdfsScopeDescription](./Add-AdfsScopeDescription.md)

[Get-AdfsScopeDescription](./Get-AdfsScopeDescription.md)

[Set-AdfsScopeDescription](./Set-AdfsScopeDescription.md)

