---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: 81E78132-AA72-4CF2-8F90-38602F8E25EA
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Remove-WebConfigurationProperty

## SYNOPSIS
Removes an IIS configuration property.

## SYNTAX

```
Remove-WebConfigurationProperty -Name <String> [-Clr <String>] [-AtElement <Hashtable>] [-AtIndex <Int32>]
 [-AtName <String>] [-Force] [-Location <String[]>] [-Filter] <String[]> [[-PSPath] <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Removes an IIS configuration property.

## EXAMPLES

### -------------- EXAMPLE 1: Remove the first binding on a site. --------------
```
IIS:\>Remove-WebconfigurationProperty '/system.applicationHost/sites/site[@name="Default Web Site"]' -Name Bindings.collection -AtIndex 0
```

Removes the first binding on the Default Web Site.

## PARAMETERS

### -AtElement
The element at which the configuration property is removed.

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
The index at which the configuration property is removed.

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
The name of the configuration property at which the property is removed.

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
Version of the .NET framework in the form vn.n, such as v4.0 or v2.0.
The default is v4.0.
This parameter is used only when PSPath is set to either Machine or Machine/Webroot.
If PSPath is not set to one of these values and the Clr parameter is set, PowerShell ignores the value of Clr and returns a warning.

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
Specifies the IIS configuration section or an XPath query that returns a configuration element.

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
When theForceparameter is used, it causes the configuration property to be removed from a level in the configuration hierarchy above an existing lock.

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
The location of the configuration property.
Location tags are frequently used for configuration settings that must be set more precisely than per application or per virtual directory.
For example, a setting for a particular file or directory could use a location tag.
Location tags are also used if a particular section is locked.
In such an instance, the configuration system would have to use a location tag in one of the parent configuration files.

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

### -Name
The name of the configuration property to remove.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PSPath
Specifies the configuration path.
This can be either an IIS configuration path in the formatcomputer name/webroot/apphost, or the IIS module path in this format IIS:\sites\Default Web Site.

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

## OUTPUTS

## NOTES

## RELATED LINKS

