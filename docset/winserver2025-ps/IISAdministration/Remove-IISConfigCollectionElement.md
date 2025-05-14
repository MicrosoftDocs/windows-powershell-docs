---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/remove-iisconfigcollectionelement?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-IISConfigCollectionElement
---

# Remove-IISConfigCollectionElement

## SYNOPSIS
Removes a configuration element object from an IIS configuration collection.

## SYNTAX

```
Remove-IISConfigCollectionElement [-ConfigCollection] <ConfigurationElementCollection>
 [[-ConfigAttribute] <Hashtable>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-IISConfigCollectionElement** cmdlet removes a ConfigurationElement from a given Internet Information Services (IIS) ConfigurationCollection.

## EXAMPLES

### Example 1: Remove a file name from the list of default documents
```
PS C:\> $ConfigSection = Get-IISConfigSection -SectionPath "system.webServer/defaultDocument"
PS C:\> Get-IISConfigCollection $ConfigSection "Files" | Remove-IISConfigCollectionElement  -ConfigAttribute @{"Value" = "MyDefDoc.htm"}
```

This command removes a configuration entry from the list of default documents.

## PARAMETERS

### -ConfigAttribute
Specifies a hashtable of the attributes to match while searching for the configuration elements to delete in the collection.
For the configuration attributes that are not specified, no filtering will be done.
If you omit this parameter, all the elements in the collection are deleted.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigCollection
Specifies the ConfigurationCollection from which the matching ConfigurationElements will be removed.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
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

[Get-IISConfigCollectionElement](./Get-IISConfigCollectionElement.md)

[New-IISConfigCollectionElement](./New-IISConfigCollectionElement.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

