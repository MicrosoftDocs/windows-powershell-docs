---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/grant-adfsapplicationpermission?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Grant-AdfsApplicationPermission
---

# Grant-AdfsApplicationPermission

## SYNOPSIS
Grants application permission.

## SYNTAX

### ClientRoleIdentifier (Default)
```
Grant-AdfsApplicationPermission [-ClientRoleIdentifier] <String> [-ServerRoleIdentifier] <String>
 [[-ScopeNames] <String[]>] [-Description <String>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PermitAllRegisteredClients
```
Grant-AdfsApplicationPermission [-AllowAllRegisteredClients] [-ServerRoleIdentifier] <String>
 [[-ScopeNames] <String[]>] [-Description <String>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Grant-AdfsApplicationPermission** cmdlet grants application permission in Active Directory Federation Services (AD FS).

## EXAMPLES

## PARAMETERS

### -AllowAllRegisteredClients
Indicates whether to allow all registered clients.

```yaml
Type: SwitchParameter
Parameter Sets: PermitAllRegisteredClients
Aliases:
Accepted values: true

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientRoleIdentifier
Specifies a client role identifier.

```yaml
Type: String
Parameter Sets: ClientRoleIdentifier
Aliases:

Required: True
Position: 0
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

### -ScopeNames
Specifies an array of scope names.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerRoleIdentifier
Specifies a server role identifier.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Management.Automation.SwitchParameter

SwitchParameter objects are received by the *AllowAllRegisteredClients* parameter.

### System.String

String objects are received by the *ClientRoleIdentifier*, *Description*, *ScopeNames*, and *ServerRoleIdentifier* parameters.

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.OAuthPermission

Returns the new OAuthPermission object when the PassThru parameter is specified. By default, this cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-AdfsApplicationPermission](./Get-AdfsApplicationPermission.md)

[Revoke-AdfsApplicationPermission](./Revoke-AdfsApplicationPermission.md)

[Set-AdfsApplicationPermission](./Set-AdfsApplicationPermission.md)

