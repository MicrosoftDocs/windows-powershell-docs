---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/get-adfsserverapplication?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsServerApplication
---

# Get-AdfsServerApplication

## SYNOPSIS
Gets configuration settings for a server application role for an application in AD FS.

## SYNTAX

### Identifier (Default)
```
Get-AdfsServerApplication [[-Identifier] <String[]>] [<CommonParameters>]
```

### Name
```
Get-AdfsServerApplication [-Name] <String[]> [<CommonParameters>]
```

### ApplicationObject
```
Get-AdfsServerApplication [-Application] <ServerApplication> [<CommonParameters>]
```

### ApplicationGroupIdentifier
```
Get-AdfsServerApplication [-ApplicationGroupIdentifier] <String> [<CommonParameters>]
```

### ApplicationGroupObject
```
Get-AdfsServerApplication [-ApplicationGroup] <ApplicationGroup> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsServerApplication** cmdlet gets configuration settings for a server application role for an application in Active Directory Federation Services (AD FS).

## EXAMPLES

## PARAMETERS

### -Application
Specifies the server application to get.

```yaml
Type: ServerApplication
Parameter Sets: ApplicationObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ApplicationGroup
Specifies the application group from which to get server applications.

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
Specifies the ID of the application group from which to get server applications.

```yaml
Type: String
Parameter Sets: ApplicationGroupIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identifier
Specifies an array of IDs of the application groups from which to get server applications.

```yaml
Type: String[]
Parameter Sets: Identifier
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array of names of the application groups from which to get server applications.

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

### System.String[]
Microsoft.IdentityServer.Management.Resources.ServerApplication
Microsoft.IdentityServer.Management.Resources.ApplicationGroup

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.ServerApplication
ADUserPrincipalName                               string
ApplicationGroupIdentifier                        string
ClientSecret                                      string
Description                                       string
Enabled                                           bool
Identifier                                        string
JWKSUri                                           uri
JWTSigningCertificateRevocationCheck              Microsoft.IdentityServer.PolicyModel.Configuration.RevocationSetting
JWTSigningKeys                                    System.Collections.Generic.IDictionary[string,System.Object]
Name                                              string
RedirectUri                                       string[]

### Microsoft.IdentityServer.PolicyModel.Configuration.RevocationSetting

RevocationSetting
{
   None = 0,
   CheckEndCert = 1,
   CheckEndCertCacheOnly = 2,
   CheckChain = 3,
   CheckChainCacheOnly = 4,
   CheckChainExcludeRoot = 5,
   CheckChainExcludeRootCacheOnly = 6,
}

## NOTES
Microsoft.IdentityServer.Management.Resources.ServerApplication inherits from Microsoft.IdentityServer.Management.Resources.ClientApplication object and implements the Microsoft.IdentityServer.Management.Resources.IApplication interface.

Microsoft.IdentityServer.Management.Resources.ClientApplication

ApplicationGroupIdentifier                        string
Description                                       string
Enabled                                           bool
Identifier                                        string
Name                                              string
RedirectUri                                       string[]

Microsoft.IdentityServer.Management.Resources.IApplication

ApplicationGroupIdentifier                        string
Enabled                                           bool
Name                                              string

## RELATED LINKS

[Add-AdfsServerApplication](./Add-AdfsServerApplication.md)

[Remove-AdfsServerApplication](./Remove-AdfsServerApplication.md)

[Set-AdfsServerApplication](./Set-AdfsServerApplication.md)
