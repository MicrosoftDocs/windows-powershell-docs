---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
ms.assetid: 7498D415-277F-448F-94B9-70BCB8C46DEF
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# New-ADFSOrganization

## SYNOPSIS
Creates a new organization information object.

## SYNTAX

```
New-ADFSOrganization -DisplayName <String> -OrganizationUrl <Uri> [-Name <String>] [<CommonParameters>]
```

## DESCRIPTION
The New-ADFSOrganization cmdlet creates a new information object for an organization in Active Directory Federation Services (AD FS) 2.0 .

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>New-ADFSOrganization -DisplayName Fabrikam -OrganizationUrl http://fabrikam.com
```

Description

-----------

Adds a new organization named Fabrikam in the Federation Service.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.Organization
A class structure that represents the organization object for the Federation Service.

## NOTES
* You can publish this information by using the Set-ADFSProperties cmdlet.

## RELATED LINKS
