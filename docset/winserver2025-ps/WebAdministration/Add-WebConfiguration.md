---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/add-webconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WebConfiguration
---

# Add-WebConfiguration

## SYNOPSIS
Adds a collection element to an IIS configuration collection.

## SYNTAX

```
Add-WebConfiguration [-Value <PSObject>] [-Clr <String>] [-AtElement <Hashtable>] [-AtIndex <Int32>]
 [-AtName <String>] [-Force] [-Location <String[]>] [-Filter] <String[]> [[-PSPath] <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-WebConfiguration** cmdlet adds a collection element to an existing Internet Information Services (IIS) configuration collection.

## EXAMPLES

### Example 1: Add a new default document
```
IIS:\> Add-WebConfiguration -Filter "//defaultDocument/files" -PSPath "IIS:\sites\Default Web Site" -AtIndex 0 -Value @{value="new-index.html"}
```

This command adds a new default document to the default document collection of the default website.
By specifying a value of 0 for the *atIndex* parameter, the new default document is inserted at the top of the list.

## PARAMETERS

### -AtElement
Specifies the element in the collection location at which this cmdlet inserts the value.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -AtIndex
Specifies the index at which this cmdlet inserts the value.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -AtName
Specifies the name at which this cmdlet inserts the value.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Clr
Specifies the version of the .NET Framework in the form vn.n, such as v4.0 or v2.0.
The default is v4.0.
Specify this parameter only when the *PSPath* parameter is set to either Machine or Machine/Webroot.
If *PSPath* is not set to one of these values and the *Clr* parameter is set, Windows PowerShell® ignores the value of *Clr* and returns a warning.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -Filter
Specifies the IIS configuration section or an XPath query that returns either a configuration section or a configuration element that contains a collection.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the creation of a configuration, and overrides existing element settings.

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

### -Location
Specifies the location to which this cmdlet writes the configuration.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PSPath
Specifies the configuration path.
This path can be either an IIS configuration path in the format computer name/webroot/apphost, or the IIS module path in the format IIS:\sites\Default Web Site.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Value
Specifies the value to add to the configuration collection.
You can specify a single value or a value/key combination in a hash table.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PSObject

## OUTPUTS

### PSObject

## NOTES

## RELATED LINKS

[Add-WebConfigurationProperty](./Add-WebConfigurationProperty.md)

[Set-WebConfiguration](./Set-WebConfiguration.md)

