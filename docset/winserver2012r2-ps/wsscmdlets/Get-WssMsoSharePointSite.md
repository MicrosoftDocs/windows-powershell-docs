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
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssmsosharepointsite?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssMsoSharePointSite
---

# Get-WssMsoSharePointSite

## SYNOPSIS
Gets SharePoint Online site configuration.

## SYNTAX

```
Get-WssMsoSharePointSite [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssMsoSharePointSite** cmdlet gets SharePoint Online site configuration.
A office_365_1 site stores the SharePoint Online site configuration.

## EXAMPLES

### Example 1: Get site configuration details
```
PS C:\> Get-WssMSOSharePointSite


Id                       : 0a2d5783-cfff-4ec2-bf34-539121f5fbbc
Title                    : Contoso Team Site
Description              :
Uri                      : https://contoso.sharepoint.com/
SubSitesRelativeUri      : {}
ParentSite               :
Libraries                : {SharePointLibrary { Id=5d92ec0b-da7d-4855-a81b-69b78020011f, Title=Documents,
RelativeUri=/Shared%20Documents }}
HasUniqueRoleAssignments : True
RoleAssignments          : {3, 4, 5, 6...}
```

This command gets the SharePoint site configuration details.

### 1:
```
PS C:\>
```

## PARAMETERS

### -Name
Specifies a SharePoint site name.
The cmdlet gets the site configuration for a SharePoint site that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
Name

Type: System.String

Description: Name of the SharePoint site

## OUTPUTS

### SharePointSite[]

## NOTES

## RELATED LINKS

