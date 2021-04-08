---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: CC399FA8-2684-41E9-A487-2329460E1829
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-WebConfigurationProperty

## SYNOPSIS
Gets an IIS configuration property at the specified path.

## SYNTAX

```
Get-WebConfigurationProperty -Name <String[]> [-Recurse] [-Clr <String>] [-Location <String[]>]
 [-Filter] <String[]> [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The Get-WebConfigurationProperty cmdlet is similar to the Get-WebConfiguration cmdlet, but Get-WebConfigurationProperty supports globbing (wildcards).

## EXAMPLES

### -------------- EXAMPLE 1: Return the Default Documents for the Default Web Site --------------
```
C:\PS>Get-WebConfigurationProperty -Filter //defaultDocument/files/add -PSPath 'IIS:\Sites\Default Web Site' -Name value | select value
```

Returns a list of the default documents associated with the Default Web Site.

Default.htm

Default.asp

Index.htm

Index.html

Iisstart.htm

Default.aspx

### -------------- EXAMPLE 2: Show handlers mapped to ASPNET_ISAPI.DLL --------------
```
C:\PS>Get-WebConfigurationProperty //handlers 'IIS:\sites\Default Web Site' -Property Collection[scriptProcessor="*aspnet_isapi.dll"] | select path,name
```

Demonstrates how to get the handlers mapped to aspnet_isapi.dll.

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
The name of the property to get.

```yaml
Type: String[]
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
This can be either an IIS configuration path in the format computer name/webroot/apphost, or the IIS module path in this format IIS:\sites\Default Web Site.

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

### -Recurse
When theRecurseparameter is specified, the cmdlet returns the properties of nodes contained within the hierarchy of the specified node.

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

### PSObject

## OUTPUTS

### PSObject

## NOTES

## RELATED LINKS

[Get-WebConfiguration](./Get-WebConfiguration.md)

[Set-WebConfigurationProperty](./Set-WebConfigurationProperty.md)

