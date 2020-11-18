---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: 9148844F-816B-4F27-BB55-A38F4F353241
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
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
The Set-WebConfigurationProperty cmdlet changes the value of an IIS configuration property.
The element can be specified as a configuration section or an XPath query.
Globbing, the use of wildcards, is supported.

## EXAMPLES

### -------------------------- EXAMPLE 1 -------------------------- 
```
IIS:\>Set-WebConfigurationProperty "//handlers/add[@path='*.aspx']" -PSPath IIS:\ -Name path -Value "*.mspx"
```

The cmdlet changes all handler paths to *.mspx that were mapped to *.aspx.

### -------------------------- EXAMPLE 2 -------------------------- 
```
IIS:\>set-webconfigurationproperty '/system.applicationHost/sites/site[@name="DemoSite"]' -PSPath IIS:\ -Name Bindings -Value (@{protocol="http";bindingInformation="*:80:DemoSite1"},@{protocol="http";bindingInformation="*:80:DemoSite2"})
```

The cmdlet sets new bindings on an existing Web site.
The original bindings are replaced.

### -------------------------- EXAMPLE 3 -------------------------- 
```
IIS:\>set-webconfigurationproperty 'system.webserver/security/authentication/basicauthentication' -PSPath 'IIS:\sites\default web site\' -Name defaultlogondomain -Value 'contoso.com'
```

The cmdlet sets the default domain of Basic Authentication settings on an existing Web site. Note that for this example to work, Custom Site Delegation for this type of Authentication must be set to Read/Write at the site level.

## PARAMETERS

### -AtElement
The element at which the configuration property is set.

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
The index at which the configuration property is set.

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
The name of the collection property for which the value is set.

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
If the Force parameter is used it causes the configuration property setting to be set at a level in the configuration hierarchy above a lock in the configuration.

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
Specifies an object that contains values to set for configuration properties.

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
The location of the configuration setting.
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
The name of the configuration property to change.

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

### -Value
The value of the configuration setting to change.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PSObject

## OUTPUTS

### PSObject

## NOTES

## RELATED LINKS

