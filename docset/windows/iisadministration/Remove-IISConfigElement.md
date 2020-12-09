---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
keywords: powershell, cmdlet
ms.assetid: D59E7781-7C00-42E6-A7B1-42BE16ED5CD4
manager: dansimp
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Remove-IISConfigElement
ms.author: v-kaunu
ms.reviewer:
---

# Remove-IISConfigElement

## SYNOPSIS
Removes a specified configuration element.

## SYNTAX

```
Remove-IISConfigElement [-ConfigElement] <ConfigurationElement> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-IISConfigElement** cmdlet deletes a specified configuration element.
This affectively causes that configuration element to inherit from the parents, if any, or use the default value as described in the schema.
If the configuration element that is being removed is a collection element, it is removed from the collection, in which case the functionality is equivalent to Remove-IISConfigCollectionElement.

## EXAMPLES

### Example 1: Remove a configuration element from an IIS website
```
PS C:\> Get-IISConfigSection "system.webServer/defaultDocument" -CommitPath "Default Web Site" | Remove-IISConfigElement
```

This command removes a configuration section from a web configuration contained in IIS website Default Web Site.

## PARAMETERS

### -ConfigElement
Specifies the Internet Information Services (IIS) ConfigurationSection or ConfigurationElement to be deleted.

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

### Microsoft.Web.Administration.ConfigurationElement

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-IISConfigElement](./Get-IISConfigElement.md)

[Remove-IISConfigCollectionElement](./Remove-IISConfigCollectionElement.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

