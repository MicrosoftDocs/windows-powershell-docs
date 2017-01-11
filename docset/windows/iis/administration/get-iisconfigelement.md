---
author: brianlic-msft
description: 
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-IISConfigElement
ms.assetid: 99FBD9F4-0DA9-4359-8483-2A2D256049A6
---

# Get-IISConfigElement

## SYNOPSIS
Gets a configuration element object from an IIS configuration section or a configuration element.

## SYNTAX

```
Get-IISConfigElement [-ConfigElement] <ConfigurationElement> [[-ChildElementName] <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-IISConfigElement** cmdlet gets a child ConfigurationElement object from either a ConfigurationSection or a ConfigurationElement.

## EXAMPLES

### Example 1: Get a configuration element for an IIS website
```
PS C:\>$ConfigSection = Get-IISConfigSection -SectionPath "system.applicationHost/sites"
PS C:\> $SitesCollection = Get-IISConfigCollection -ConfigElement $ConfigSection
PS C:\> $Site = Get-IISConfigCollectionElement -ConfigCollection $SitesCollection -ConfigAttribute @{"name" = "Default Web Site"}
PS C:\> $Elem = Get-IISConfigElement -ConfigElement $Site -ChildElementName "limits"
PS C:\> Get-IISConfigAttributeValue -ConfigElement $Elem -AttributeName "MaxUrlSegments"
```

This command returns the configuration element limits for the Default Web Site into the Windows PowerShell variable $Elem.

## PARAMETERS

### -ChildElementName
Specifies the name of the child ConfigurationElement to be returned.
If this parameter is omitted, all the child elements for the given parent are returned.

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

### -ConfigElement
Specifies the IIS ConfigurationSection or ConfigurationElement for which the child ConfigurationElement is returned.

```yaml
Type: ConfigurationElement
Parameter Sets: (All)
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

### Microsoft.Web.Administration.ConfigurationElement, System.String

## OUTPUTS

### Microsoft.Web.Administration.ConfigurationElement

## NOTES

## RELATED LINKS

[Remove-IISConfigElement](./Remove-IISConfigElement.md)

[IIS Administration Cmdlets for Windows PowerShell](./index.md)

