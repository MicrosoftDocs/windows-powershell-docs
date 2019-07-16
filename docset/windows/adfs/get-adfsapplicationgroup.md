---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: ADFS
ms.assetid: 592B5570-5A73-48AB-B438-68E7BDD299FE
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version:
schema: 2.0.0
title: Get-AdfsApplicationGroup
ms.reviewer:
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]
Microsoft.IdentityServer.Management.Resources.ApplicationGroup

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.ApplicationGroup
ApplicationGroupIdentifier  string
Applications                Microsoft.IdentityServer.Management.Resources.IApplication[]
Description                 string
Enabled                     bool
Name                        string

### Microsoft.IdentityServer.Management.Resources.IApplication
ADUserPrincipalName                   string
ApplicationGroupIdentifier            string
ClientSecret                          string
Description                           string
Enabled                               bool
Identifier                            string
JWKSUri                               uri
JWTSigningCertificateRevocationCheck  Microsoft.IdentityServer.PolicyModel.Configuration.RevocationSetting
JWTSigningKeys                        System.Collections.Generic.IDictionary[string,System.Object]
Name                                  string
RedirectUri                           string[]

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

## RELATED LINKS

[Disable-AdfsApplicationGroup](./Disable-AdfsApplicationGroup.md)

[Enable-AdfsApplicationGroup](./Enable-AdfsApplicationGroup.md)

[New-AdfsApplicationGroup](./New-AdfsApplicationGroup.md)

[Remove-AdfsApplicationGroup](./Remove-AdfsApplicationGroup.md)

[Set-AdfsApplicationGroup](./Set-AdfsApplicationGroup.md)
