---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/add-adfsscopedescription?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-AdfsScopeDescription
---

# Add-AdfsScopeDescription

## SYNOPSIS
Adds a scope description in AD FS.

## SYNTAX

```
Add-AdfsScopeDescription [-Name] <String> [-Description <String>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-AdfsScopeDescription** cmdlet adds a scope description that represents the scope of access granted to resources and applications in Active Directory Federation Services (AD FS).

## EXAMPLES

## PARAMETERS

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

### -Name
Specifies the name of the scope description.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### System.String

String objects are received by the *Description* and *Name* parameters.

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.OAuthScopeDescription

Returns the new OAuthScopeDescription object when the *PassThru* parameter is specified. By default, this cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-AdfsScopeDescription](./Get-AdfsScopeDescription.md)

[Remove-AdfsScopeDescription](./Remove-AdfsScopeDescription.md)

[Set-AdfsScopeDescription](./Set-AdfsScopeDescription.md)

