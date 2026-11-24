---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/get-iisconfigcollectionelement?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IISConfigCollectionElement
---

# Get-IISConfigCollectionElement

## SYNOPSIS
Gets a configuration element object from an IIS configuration collection.

## SYNTAX

```
Get-IISConfigCollectionElement [-ConfigCollection] <ConfigurationElementCollection>
 [[-ConfigAttribute] <Hashtable>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IISConfigCollectionElement** cmdlet gets a **ConfigurationElement** object that is part of a given ConfigurationCollection.
The returned element then can be used in further cmdlets that expect a **ConfigurationElement**.

## EXAMPLES

### Example 1: Get a configuration element for the default web site by passing the collection through a pipeline
```
PS C:\> Get-IISConfigSection -SectionPath "system.applicationHost/sites" | Get-IISConfigCollection | Get-IISConfigCollectionElement -ConfigAttribute @{"name"="Default Web Site"}
```

This command gets a configuration element for the default web site by passing the collection through a pipeline.

### Example 2: Get a configuration element using a configuration collection as a parameter
```
PS C:\> $SiteCollection = Get-IISConfigSection -SectionPath "system.applicationHost/sites" | Get-IISConfigCollection
Get-IISConfigCollectionElement -ConfigCollection $SiteCollection -ConfigAttribute @{"name"="Default Web Site"}
```

This command gets a configuration element for the default web site and then stores the element into variable $SiteCollection.

## PARAMETERS

### -ConfigAttribute
Specifies a hashtable of the attributes for the configuration element to be inserted.
The cmdlet will fail if any required attributes are omitted from this table.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigCollection
Specifies the **ConfigurationCollection** object for which the collection elements will be returned.
If a ConfigurationCollection is previously obtained and assigned to a variable, you cannot pass it to this cmdlet through the pipeline because the pipeline engine will try to enumerate, passing ConfigurationElement objects instead.
Try either passing the whole Get-IISConfigCollection cmdlet into the pipeline or use it as a parameter for correct results.

```yaml
Type: ConfigurationElementCollection
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

### Microsoft.Web.Administration.ConfigurationElementCollection

### System.Collections.Hashtable

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[New-IISConfigCollectionElement](./New-IISConfigCollectionElement.md)

[Remove-IISConfigCollectionElement](./Remove-IISConfigCollectionElement.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

