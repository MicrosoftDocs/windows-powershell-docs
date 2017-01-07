---
author: brianlic-msft
description: 
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AdfsApplicationPermission
ms.assetid: EAE924E8-5BC3-4D00-9ED0-96FB35B96420
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

### 1:
```

```

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Grant-AdfsApplicationPermission](./Grant-AdfsApplicationPermission.md)

[Revoke-AdfsApplicationPermission](./Revoke-AdfsApplicationPermission.md)

[Set-AdfsApplicationPermission](./Set-AdfsApplicationPermission.md)

