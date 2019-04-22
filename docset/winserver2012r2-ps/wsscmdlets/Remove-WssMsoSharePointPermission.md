---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Remove-WssMsoSharePointPermission
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 4D913B95-2B5A-44C1-9738-3C632521FA3D
ms.author: kenwith
ms.reviewer: brianlic
---

# Remove-WssMsoSharePointPermission

## SYNOPSIS
Removes a permission relationship between a sp_2013_2 user or group and a library or site.

## SYNTAX

### ByLibrary
```
Remove-WssMsoSharePointPermission [-Library] <SharePointLibrary> [[-User] <SharePointUser>]
 [<CommonParameters>]
```

### BySite
```
Remove-WssMsoSharePointPermission [-Site] <SharePointSite> [[-User] <SharePointUser>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WssMsoSharePointPermission** cmdlet removes a permission relationship between a sp_2013_1 user or group and a  sp_2013_2 library or site.
A office_365_1 site stores the  sp_online_1 library.

## EXAMPLES

### Example 1: Remove a SharePoint permission relationship
```
PS C:\>Remove-WssMsoSharePointPermission -User "Admin01"
```

This command removes sp_2013_2 permissions for the user.

### 1:
```
PS C:\>
```

## PARAMETERS

### -Library
Specifies a  sp_2013_2 library.
The cmdlet removes a permission relationship for the library that you specify.

```yaml
Type: SharePointLibrary
Parameter Sets: ByLibrary
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Site
Specifies a  sp_2013_2 site.
The cmdlet removes a permission relationship for the site that you specify.

```yaml
Type: SharePointSite
Parameter Sets: BySite
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -User
Specifies a sp_2013_2 user.
The cmdlet removes a permission relationship for the user that you specify.

```yaml
Type: SharePointUser
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsServerSolutions.O365Integration.SharePointLibrary,Microsoft.WindowsServerSolutions.O365Integration.SharePointSite
Library

Type: Microsoft.WindowsServerSolutions.O365Integration.SharePointLibrary

Description: SharePoint library

Site

Type: Microsoft.WindowsServerSolutions.O365Integration.SharePointSite

Description: SharePoint site

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssMsoSharePointPermission](./Get-WssMsoSharePointPermission.md)

[Set-WssMsoSharePointPermission](./Set-WssMsoSharePointPermission.md)

