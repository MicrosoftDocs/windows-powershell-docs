---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/get-iisconfigelement?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IISConfigElement
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
PS C:\> $ConfigSection = Get-IISConfigSection -SectionPath "system.applicationHost/sites"
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
Position: 2
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
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Web.Administration.ConfigurationElement

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Remove-IISConfigElement](./Remove-IISConfigElement.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

