---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/add-webconfigurationproperty?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WebConfigurationProperty
---

# Add-WebConfigurationProperty

## SYNOPSIS
Adds a property to an IIS configuration section.

## SYNTAX

```
Add-WebConfigurationProperty -Name <String> [-Type <String>] [-Value <PSObject>] [-Clr <String>]
 [-AtElement <Hashtable>] [-AtIndex <Int32>] [-AtName <String>] [-Force] [-Location <String[]>]
 [-Filter] <String[]> [[-PSPath] <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-WebConfigurationProperty** cmdlet adds a property to an Internet Information Services (IIS) configuration section.
Globbing is supported.

## EXAMPLES

### Example 1: Adding a default document
```
IIS:\> Add-WebConfigurationProperty -Filter "//defaultDocument/files" -PSPath "IIS:\sites\Default Web Site" -AtIndex 0 -Name "Collection" -Value "new-index.html"
```

This command adds a new default document named new-index.html to the top of the list of existing documents.

## PARAMETERS

### -AtElement
Specifies the element at which this cmdlet inserts the value.

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
Specifies the index at which this cmdlet inserts the property.

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
Specifies the property name at which this cmdlet inserts the property.

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
If *PSPath* is not set to one of these values and the *Clr* parameter is set, Windows PowerShell ignores the value of *Clr* and returns a warning.

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
Forces the property to be written.
If a lock exists, the property is written at a level in the configuration above the lock.

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
Specifies the location of the configuration property setting.
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
Specifies the name of the IIS configuration property to add.

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

### -Type
Specifies the type of property that this cmdlet adds.

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

### -Value
Specifies the value of the configuration property that this cmdlet adds.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WebConfigurationProperty](./Get-WebConfigurationProperty.md)

[Remove-WebConfigurationProperty](./Remove-WebConfigurationProperty.md)

[Set-WebConfigurationProperty](./Set-WebConfigurationProperty.md)

