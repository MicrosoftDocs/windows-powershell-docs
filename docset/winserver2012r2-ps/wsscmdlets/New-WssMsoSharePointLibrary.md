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
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/new-wssmsosharepointlibrary?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-WssMsoSharePointLibrary
---

# New-WssMsoSharePointLibrary

## SYNOPSIS
Creates a sp_online_2 library.

## SYNTAX

```
New-WssMsoSharePointLibrary [-Name] <String> [[-Description] <String>] [[-LibraryType] <SharePointLibraryType>]
 [[-Site] <SharePointSite>] [-EnableVersioning] [-ForceCheckout] [<CommonParameters>]
```

## DESCRIPTION
The **New-WssMsoSharePointLibrary** cmdlet creates a sp_online_1 library.
A office_365_1 site stores the sp_online_2 library.

## EXAMPLES

### Example 1: Create a SharePoint library
```
PS C:\> $Site = Get-WssMSOSharePointSite | Select-Object -First 1
PS C:\> New-WssMsoSharePointLibrary -Name "Documents" -Description "SharePoint library used to share documents." -LibraryType "DocumentLibrary" -Site $Site -EnableVersioning
SharePointLibraryType: DocumentLibrary = 101, PictureLibrary = 109, WebPageLibrary = 119
```

The first command uses the Get-WssMsoSharePointSite cmdlet to get a site, and saves the result in the $Site variable.

The second command creates a SharePoint Online library in the site specified in the $Site variable.

## PARAMETERS

### -Description
Specifies a description of a sp_online_2 library.
The cmdlet creates the library with the description that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableVersioning
Indicates that versioning is enabled for this library.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ForceCheckout
Indicates that force checkout is enabled for this library.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LibraryType
Specifies the type of a sp_online_2 library.
The cmdlet creates the library with the type that you specify.

```yaml
Type: SharePointLibraryType
Parameter Sets: (All)
Aliases: 
Accepted values: NoListTemplate, DocumentLibrary, PictureLibrary, WebPageLibrary, InvalidType

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a library.
The cmdlet creates the sp_online_2 library with the name that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Site
Specifies a sp_online_2 site.
The cmdlet creates the library in the site that you specify.
If you do not specify this parameter, the cmdlet creates the library under the default site.

```yaml
Type: SharePointSite
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
Name

Type: System.String

Description: Name of the SharePoint library

## OUTPUTS

### SharePointLibrary

## NOTES

## RELATED LINKS

[Get-WssMsoSharePointLibrary](./Get-WssMsoSharePointLibrary.md)

[Remove-WssMsoSharePointLibrary](./Remove-WssMsoSharePointLibrary.md)

[Set-WssMsoSharePointLibrary](./Set-WssMsoSharePointLibrary.md)

