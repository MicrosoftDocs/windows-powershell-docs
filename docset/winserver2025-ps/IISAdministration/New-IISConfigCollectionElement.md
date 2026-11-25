---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/new-iisconfigcollectionelement?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-IISConfigCollectionElement
---

# New-IISConfigCollectionElement

## SYNOPSIS
Creates a new configuration element object in an IIS configuration collection.

## SYNTAX

```
New-IISConfigCollectionElement [-ConfigCollection] <ConfigurationElementCollection>
 [-ConfigAttribute] <Hashtable> [[-AddAt] <UInt32>] [-Passthru] [<CommonParameters>]
```

## DESCRIPTION
The **New-IISConfigCollectionElement** cmdlet creates a new ConfigurationElement in a given Internet Information Services (IIS) ConfigurationCollection.

## EXAMPLES

### Example 1: Add a new file name to list of default documents
```
PS C:\> $ConfigSection = Get-IISConfigSection -SectionPath "system.webServer/defaultDocument"
PS C:\> $DefaultDocumentCollection = Get-IISConfigCollection -ConfigElement $ConfigSection -CollectionName "files"
PS C:\> New-IISConfigCollectionElement
  -ConfigCollection $DefaultDocumentCollection -ConfigAttribute @{"Value" = "MyDefDoc.htm"}
```

This command creates an entry in the list of default documents.

### Example 2: Add a new file name to the top of the list of default documents
```
PS C:\> Get-IISConfigSection -SectionPath "system.webServer/defaultDocument" | Get-IISConfigCollection -CollectionName "files" | New-IISConfigCollectionElement  -ConfigAttribute @{Value = "MyDefDoc.htm"} -AddAt 0
```

This command creates a new entry in the list of default documents, and makes this new entry the first item in the collection.
This is done by setting the value of the *AddAt* parameter to 0; the first item in a collection is always item number 0.

## PARAMETERS

### -AddAt
Specifies the collection index for the new configuration element; by default, new elements are added to the end of the collection.
The collection index specifies the ordering of items in the collection: the first item in the collection is item 0; the second item in the collection is item 1; and so on.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigAttribute
Specifies a hashtable of the attributes for the configuration element to be inserted.
The cmdlet will fail if any required attributes are omitted from this table.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigCollection
Specifies the **ConfigurationCollection** object to which the new collection element will be added.
If a **ConfigurationCollection** is previously obtained and assigned to a variable, you cannot pass it to this cmdlet through the pipeline because the pipeline engine will try to enumerate it, passing **ConfigurationElement** objects instead.
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

### -Passthru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Web.Administration.ConfigurationElementCollection

### System.Collections.Hashtable

### System.UInt32

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-IISConfigCollectionElement](./Get-IISConfigCollectionElement.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

