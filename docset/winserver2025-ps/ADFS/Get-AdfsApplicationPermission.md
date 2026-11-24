---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/get-adfsapplicationpermission?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsApplicationPermission
---

# Get-AdfsApplicationPermission

## SYNOPSIS
Gets permission for an application.

## SYNTAX

### Identifier (Default)
```
Get-AdfsApplicationPermission [[-Identifiers] <String[]>] [<CommonParameters>]
```

### ClientRoleIdentifier
```
Get-AdfsApplicationPermission [[-ClientRoleIdentifiers] <String[]>] [<CommonParameters>]
```

### ServerRoleIdentifier
```
Get-AdfsApplicationPermission [[-ServerRoleIdentifiers] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsApplicationPermission** cmdlet gets permission for an application in Active Directory Federation Services (AD FS).

## EXAMPLES

## PARAMETERS

### -ClientRoleIdentifiers
Specifies an array of client role identifiers.

```yaml
Type: String[]
Parameter Sets: ClientRoleIdentifier
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Identifiers
Specifies an array of identifiers.

```yaml
Type: String[]
Parameter Sets: Identifier
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerRoleIdentifiers
Specifies an array of server role identifiers.

```yaml
Type: String[]
Parameter Sets: ServerRoleIdentifier
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

String objects are received by the *ClientRoleIdentifiers*, *Identifiers*, and *ServerRoleIdentifiers* parameters.

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.OAuthPermission

Returns one or more OAuthPermission objects that represent the application permissions for the Federation Service.

## NOTES

## RELATED LINKS

[Grant-AdfsApplicationPermission](./Grant-AdfsApplicationPermission.md)

[Revoke-AdfsApplicationPermission](./Revoke-AdfsApplicationPermission.md)

[Set-AdfsApplicationPermission](./Set-AdfsApplicationPermission.md)
