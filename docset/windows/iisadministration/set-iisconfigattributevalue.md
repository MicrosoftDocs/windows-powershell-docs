---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
keywords: powershell, cmdlet
ms.assetid: E38E7E60-8D04-4257-96DC-979975E9ACB0
manager: dansimp
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-IISConfigAttributeValue
ms.author: v-anbarr
ms.reviewer:
---

# Set-IISConfigAttributeValue

## SYNOPSIS
Sets a configuration attribute value for an IIS configuration section or configuration element attribute.

## SYNTAX

```
Set-IISConfigAttributeValue [-ConfigElement] <ConfigurationElement> [-AttributeName] <String>
 [-AttributeValue] <Object> [<CommonParameters>]
```

## DESCRIPTION
The **Set-IISConfigAttributeValue** cmdlet sets a configuration attribute value from an Internet Information Services (IIS) configuration section attribute or a configuration element attribute.
The value set is for the given ConfigurationElement and not necessarily the effective value for a given site / virtual directory / folder etc.
To set the effective attribute values, always retrieve the configuration element by specifying the commit path as the deepest level possible.

## EXAMPLES

### Example 1: Set the value of a configuration attribute
```
PS C:\> $ConfigSection = Get-IISConfigSection -SectionPath "system.applicationHost/sites"
PS C:\> $SitesCollection = Get-IISConfigCollection -ConfigElement $ConfigSection
PS C:\> $Site = Get-IISConfigCollectionElement -ConfigCollection $SitesCollection -ConfigAttribute @{"name" = "Default Web Site"}
PS C:\> $Elem = Get-IISConfigElement -ConfigElement $Site -ChildElementName "limits"
PS C:\> Set-IISConfigAttributeValue -ConfigElement $Elem -AttributeName "MaxUrlSegments" -AttributeValue 16
```

This command sets the value of the configuration attribute MaxUrlSegments for the IIS website named Default Web Site to 16.

## PARAMETERS

### -AttributeName
Specifies the name of the attribute for which the value will be set.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AttributeValue
Specifies the new value of the attribute.

```yaml
Type: Object
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigElement
Specifies the IIS ConfigurationSection or ConfigurationElement for which the attribute value will be looked up.

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

### Microsoft.Web.Administration.ConfigurationElement, System.String, System.Object

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-IISConfigAttributeValue](./Get-IISConfigAttributeValue.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

