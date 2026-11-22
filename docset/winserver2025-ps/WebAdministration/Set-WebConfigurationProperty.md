---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/set-webconfigurationproperty?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WebConfigurationProperty
---

# Set-WebConfigurationProperty

## SYNOPSIS
Changes the value of an IIS configuration property.

## SYNTAX

### InputPSObject (Default)
```
Set-WebConfigurationProperty -Name <String> -Value <PSObject> [-Clr <String>] [-AtElement <Hashtable>]
 [-AtIndex <Int32>] [-AtName <String>] [-Force] [-Location <String[]>] [-Filter] <String[]>
 [[-PSPath] <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Set-WebConfigurationProperty -Name <String> -InputObject <Object> [-Clr <String>] [-AtElement <Hashtable>]
 [-AtIndex <Int32>] [-AtName <String>] [-Force] [-Location <String[]>] [-Filter] <String[]>
 [[-PSPath] <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WebConfigurationProperty** cmdlet changes the value of an Internet Information Services (IIS) configuration property.
Specify the element as a configuration section or an XPath query.
Globbing, or the use of wildcards, is supported.

## EXAMPLES

### Example 1: Change the extension of all handlers mapped to .aspx
```
IIS:\> Set-WebConfigurationProperty -Filter "//handlers/add[@path='*.aspx']" -PSPath "IIS:\" -Name "path" -Value "*.mspx"
```

This command changes all handler paths to *.mspx that were mapped to *.aspx.

### Example 2: Set new bindings on an existing website
```
IIS:\> Set-WebConfigurationProperty -Filter '/system.applicationHost/sites/site[@name="DemoSite"]' -PSPath "IIS:\" -Name "Bindings" -Value (@{protocol="http";bindingInformation="*:80:DemoSite1"},@{protocol="http";bindingInformation="*:80:DemoSite2"})
```

This command sets new bindings on an existing website.
The original bindings are replaced.

## PARAMETERS

### -AtElement
Specifies the element at which this cmdlet sets the configuration property.

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
Specifies the index at which this cmdlet sets the configuration property.

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
Specifies the name of the collection property for which this cmdlet sets the value.

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
Indicates that the cmdlet causes the configuration property setting to be set at a level in the configuration hierarchy above a lock in the configuration.

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

### -InputObject
Specifies an input object that contains values to set for configuration properties.

```yaml
Type: Object
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Location
Specifies the location of the configuration setting.
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
Specifies the name of the configuration property to change.

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
This path can be either an IIS configuration path in the format computer name/webroot/apphost, or the IIS module path in this format IIS:\sites\Default Web Site.

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
Specifies the value of the configuration setting that this cmdlet changes.

```yaml
Type: PSObject
Parameter Sets: InputPSObject
Aliases: v, val

Required: True
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

[Get-WebConfigurationProperty](./Get-WebConfigurationProperty.md)

[Remove-WebConfigurationProperty](./Remove-WebConfigurationProperty.md)

