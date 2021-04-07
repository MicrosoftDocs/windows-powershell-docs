---
author: Kateyanne
description: 
external help file: WssCmdlets.dll-Help.xml
manager: jasgro
Module Name: WSSCmdlets
ms.author: v-kaunu
ms.date: 12/05/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/remove-wssmsosharepointpermission?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WssMsoSharePointPermission
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

