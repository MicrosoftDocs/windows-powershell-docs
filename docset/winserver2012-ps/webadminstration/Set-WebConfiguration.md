---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: 96B02A59-C5B0-4E1E-B24E-2FF7098EBFCF
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-WebConfiguration

## SYNOPSIS
Sets the value of an IIS configuration element.

## SYNTAX

### InputPSObject (Default)
```
Set-WebConfiguration -Value <PSObject> [-Metadata <String>] [-Clr <String>] [-Force] [-Location <String[]>]
 [-Filter] <String[]> [[-PSPath] <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Set-WebConfiguration -InputObject <Object> [-Metadata <String>] [-Clr <String>] [-Force] [-Location <String[]>]
 [-Filter] <String[]> [[-PSPath] <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Set-WebConfiguration cmdlet changes the value of an IIS configuration element.
The element can be specified as a configuration section or an XPath query.

## EXAMPLES

### -------------- EXAMPLE 1: Setting new Bindings on an existing Web site --------------
```
IIS:\>Set-WebConfiguration -filter '/system.applicationHost/sites/site[@name=" DemoSite"]/bindings' -PSPath IIS:\ -value (@{protocol="http";bindingInformation="*:80:DemoSite1"},@{protocol="http";bindingInformation="*:80:DemoSite2"})
```

TheSet-WebConfigurationcmdlet is used to replace the existing bindings of the Web site named DemoSite with new bindings.

## PARAMETERS

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
When theForceparameter is used, it causes the configuration setting to be set at a level in the configuration hierarchy above a lock in the configuration.

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
Specifies an object that contains values to set for configuration elements.

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

### -Metadata
If this parameter is specified, configuration metadata such as encryption or locking settings can be changed.

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

### PSObject

## OUTPUTS

### PSObject

## NOTES

## RELATED LINKS

