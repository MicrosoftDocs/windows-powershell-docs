---
description: Sets Active Directory properties for the AD FS.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: adfs
ms.date: 09/30/2021
online version: https://docs.microsoft.com/powershell/module/adfs/set-adfsdirectoryproperties?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsDirectoryProperties
---

# Set-AdfsDirectoryProperties

## SYNOPSIS
Sets Active Directory properties for the AD FS.

## SYNTAX

```
Set-AdfsDirectoryProperties [-AddUpnSuffix <String[]>] [-RemoveUpnSuffix <String[]>]
 [-AddNetbiosName <String[]>] [-RemoveNetbiosName <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsDirectoryProperties** cmdlet sets properties for the AD FS directory.

## EXAMPLES

### Example 1: Set Active Directory properties for AD FS
```
PS> Set-AdfsDirectoryProperties -AddUpnSuffix custom.contoso.com -AddNetbiosName customDomain
```

Adds `custom.contoso.com` to the custom UPN suffix list and `customDomain` to the custom NetBIOS
name.

## PARAMETERS

### -AddNetbiosName

Specifies a list of custom allowed NetBIOS names.

AD FS auto detects NetBIOS names from the Active Directory. The specified custom NetBIOS names are
also allowed for user authentication.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddUpnSuffix

Specifies a list of custom UPN suffixes to add.

AD FS auto detects the UPN suffix names from the Active Directory. The specified custom UPN suffixes
are also allowed for user authentication.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveNetbiosName

Specifies a list of NetBIOS names to remove from the custom NetBIOS names list.

AD FS auto detects NetBIOS names from the Active Directory. The specified custom NetBIOS names are
also allowed for user authentication.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveUpnSuffix

Specifies a list of UPN suffixes to remove from the custom UPN suffix list.

AD FS auto detects the UPN suffix names from the Active Directory. The specified custom UPN suffixes
are also allowed for user authentication.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
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

### System.Object
## NOTES

## RELATED LINKS
