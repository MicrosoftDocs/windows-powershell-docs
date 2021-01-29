---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Enable-WssMsoSharePointPermissionInheritance
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: A2649EF8-D2CA-4B26-BE74-297DBCE5A8B2
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Enable-WssMsoSharePointPermissionInheritance

## SYNOPSIS
Enables permission inheritance for a SharePoint Online securable object.

## SYNTAX

### ByLibrary
```
Enable-WssMsoSharePointPermissionInheritance [-Library] <SharePointLibrary> [<CommonParameters>]
```

### BySite
```
Enable-WssMsoSharePointPermissionInheritance [-Site] <SharePointSite> [<CommonParameters>]
```

## DESCRIPTION
The **Enable-WssMsoSharePointPermissionInheritance** cmdlet enables permission inheritance for a SharePoint Online securable object.
Securable objects include sites, lists, libraries, folders, documents, or items.

## EXAMPLES

### Example 1: Enable SharePoint permission inheritance
```
PS C:\> $Library = Get-WssMsoSharePointLibrary | Select-Object -First 1
PS C:\> Enable-WssMsoSharePointPermissionInheritance -SharePointLibrary $Library
```

The first command uses the Get-WssMsoSharePointLibrary cmdlet to get a library, and stores the result in the $Library variable.

The second command enables permission inheritance for the library named $Library.

### 1:
```
PS C:\>
```

## PARAMETERS

### -Library
Specifies a SharePoint library.
The cmdlet enables permission inheritance for a library that you specify.

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
The cmdlet enables permission inheritance for a site that you specify.

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

[Disable-WssMsoSharePointPermissionInheritance](./Disable-WssMsoSharePointPermissionInheritance.md)

