---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/new-adfsorganization?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-AdfsOrganization
---

# New-AdfsOrganization

## SYNOPSIS
Creates a new organization information object.

## SYNTAX

```
New-AdfsOrganization -DisplayName <String> -OrganizationUrl <Uri> [-Name <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AdfsOrganization** cmdlet creates an information object for an organization in Active Directory Federation Services (AD FS) 2.0.

## EXAMPLES

### Example 1: Create a new organization
```
PS C:\> New-AdfsOrganization -DisplayName "Fabrikam" -OrganizationUrl https://fabrikam.com
```

This command adds a new organization named Fabrikam in the AD FS.

## PARAMETERS

### -DisplayName
Specifies the display name of the organization.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the organization.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OrganizationUrl
Specifies the URL of the organization.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.Organization
This cmdlet generates a class structure that represents the organization object for the AD FS.

## NOTES
* You can publish this information by using the **Set-AdfsProperties** cmdlet.

## RELATED LINKS

[Get-AdfsProperties](./Get-AdfsProperties.md)

[Set-AdfsProperties](./Set-AdfsProperties.md)

