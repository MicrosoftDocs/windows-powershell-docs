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
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssmsosharepointpermission?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssMsoSharePointPermission
---

# Get-WssMsoSharePointPermission

## SYNOPSIS
Gets permission settings for a SharePoint Online securable object.

## SYNTAX

### ByLibrary
```
Get-WssMsoSharePointPermission [-Library] <SharePointLibrary> [[-User] <SharePointUser>] [<CommonParameters>]
```

### BySite
```
Get-WssMsoSharePointPermission [-Site] <SharePointSite> [[-User] <SharePointUser>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssMsoSharePointPermission** cmdlet gets permission settings for a SharePoint Online securable object.
A office_365_1 site stores the SharePoint Online library.

## EXAMPLES

### Example 1: Get SharePoint permissions
```
PS C:\> $Library= Get-WssMmoSharePointLibrary | Select-Object -First 1
PS C:\> $Principal= Get-WssMsoSharePointPrincipal | Select-Object -First 1
PS C:\> Get-WssMSOSharePointObjectPermission -SecurableObject $Library -Principal $Principal
```

The first command uses the Get-WssMsoSharePointLibrary cmdlet to get a library, and stores the result in the $Library variable.

The second command uses the Get-WssMsoSharePointPrincipal cmdlet to get a SharePoint principal, and stores the result in the $Principal variable.

The last command gets the SharePoint permissions for the library named $Library and the principal named $Principal.

### 1:
```
PS C:\>
```

## PARAMETERS

### -Library
Specifies a SharePoint library.
The cmdlet gets permission settings for the library that you specify.

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
Specifies a SharePoint site.
The cmdlet gets permission settings for the site that you specify.

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
Specifies a SharePoint user.
The cmdlet gets permission settings for the user that you specify.

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

### System.String

## NOTES

## RELATED LINKS

[Remove-WssMsoSharePointPermission](./Remove-WssMsoSharePointPermission.md)

[Set-WssMsoSharePointPermission](./Set-WssMsoSharePointPermission.md)

