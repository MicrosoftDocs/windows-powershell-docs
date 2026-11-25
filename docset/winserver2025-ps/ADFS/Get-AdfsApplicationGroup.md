---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/get-adfsapplicationgroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsApplicationGroup
---

# Get-AdfsApplicationGroup

## SYNOPSIS
Gets an application group.

## SYNTAX

### ApplicationGroupIdentifier (Default)
```
Get-AdfsApplicationGroup [[-ApplicationGroupIdentifier] <String[]>] [<CommonParameters>]
```

### Name
```
Get-AdfsApplicationGroup [-Name] <String[]> [<CommonParameters>]
```

### ApplicationGroupObject
```
Get-AdfsApplicationGroup [-ApplicationGroup] <ApplicationGroup> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsApplicationGroup** cmdlet gets an Active Directory Federation Services (AD FS) application group.

## EXAMPLES

## PARAMETERS

### -ApplicationGroup
Specifies an application group.

```yaml
Type: ApplicationGroup
Parameter Sets: ApplicationGroupObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ApplicationGroupIdentifier
Specifies the ID of an application group.

```yaml
Type: String[]
Parameter Sets: ApplicationGroupIdentifier
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array of names of application groups.

```yaml
Type: String[]
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.IdentityServer.Management.Resources.ApplicationGroup

ApplicationGroup objects are received by the *ApplicationGroup* parameter.

### System.String

String objects are received by the *ApplicationGroupIdentifier* and *Name* parameters.

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.ApplicationGroup

Returns one or more ApplicationGroup objects that represent the Application Groups for the Federation Service.

## NOTES

## RELATED LINKS

[Disable-AdfsApplicationGroup](./Disable-AdfsApplicationGroup.md)

[Enable-AdfsApplicationGroup](./Enable-AdfsApplicationGroup.md)

[New-AdfsApplicationGroup](./New-AdfsApplicationGroup.md)

[Remove-AdfsApplicationGroup](./Remove-AdfsApplicationGroup.md)

[Set-AdfsApplicationGroup](./Set-AdfsApplicationGroup.md)
