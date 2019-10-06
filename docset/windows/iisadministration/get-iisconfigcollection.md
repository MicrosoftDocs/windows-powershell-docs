---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
keywords: powershell, cmdlet
ms.assetid: A8957835-831C-497B-BC59-EAFCF2D5470A
manager: dansimp
ms.date: 12/20/2016
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-IISConfigCollection
ms.author: v-anbarr
ms.reviewer:
---

# Get-IISConfigCollection

## SYNOPSIS
Gets a configuration collection object from an IIS configuration section or a configuration element.

## SYNTAX

```
Get-IISConfigCollection [-ConfigElement] <ConfigurationElement> [[-CollectionName] <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-IISConfigCollection** cmdlet gets a **ConfigurationCollection** object from either a ConfigurationSection or a ConfigurationElement. 

It is advisable to not to assign this value to a parameter and pass it in the pipeline to the next cmdlet since Windows PowerShell cannot interpret this object.
This is due to the fact that **ConfigurationCollection** implements IEnumerable and the pipeline processor enumerates each single element when used this way.
Instead either pass the whole **Get-IISConfigCollection** cmdlet in the pipeline or pass it as a parameter.

## EXAMPLES

### Example 1: Get a configuration collection from an IIS configuration element
```
PS C:\> Get-IISConfigSection -SectionPath "system.webServer/defaultDocument" | Get-IISConfigCollection -CollectionName "files"

Attributes      : {value}
ChildElements   : {}
ElementTagName  : add
IsLocallyStored : True
Methods         : 
RawAttributes   : {[value, Default.htm]} 
Schema          : Microsoft.Web.Administration.ConfigurationElementSchema

Attributes      : {value}
ChildElements   : {}
ElementTagName  : add
IsLocallyStored : True
Methods         : 
RawAttributes   : {[value, Default.asp]} 
Schema          : Microsoft.Web.Administration.ConfigurationElementSchema
```

This command gets the Files Collection for the system.webServer/defaultDocument section.

### Example 2: Get a configuration element from an IIS configuration section
```
PS C:\> Get-IISConfigSection -SectionPath "system.webServer/defaultDocument" | Get-IISConfigElement -ChildElementName "files" | Get-IISConfigCollection


Attributes      : {value}
ChildElements   : {}
ElementTagName  : add
IsLocallyStored : True
Methods         : 
RawAttributes   : {[value, Default.htm]} 
Schema          : Microsoft.Web.Administration.ConfigurationElementSchema

Attributes      : {value}
ChildElements   : {}
ElementTagName  : add
IsLocallyStored : True
Methods         : 
RawAttributes   : {[value, Default.asp]} 
Schema          : Microsoft.Web.Administration.ConfigurationElementSchema
```

This command gets the Files Element configuration object from the system.webServer/defaultDocument section then gets its default collection.
The output of the two formats are the same.

## PARAMETERS

### -CollectionName
Specifies the name of the collection to be returned.
If the name of the collection is not used, the Default Collection is returned.
Alternatively, the named collection can be retrieved by **Get-IISConfigElement** then the default collection inside this element can be retrieved.

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
Specifies the IIS ConfigurationSection or ConfigurationElement for which the ConfigurationCollection is returned.

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

### Microsoft.Web.Administration.ConfigurationElement,System.String

## OUTPUTS

## NOTES

## RELATED LINKS

[Clear-IISConfigCollection](./Clear-IISConfigCollection.md)

[Get-IISConfigElement](./Get-IISConfigElement.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

