---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/get-webconfigurationproperty?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WebConfigurationProperty
---

# Get-WebConfigurationProperty

## SYNOPSIS
Gets an IIS configuration property at a path.

## SYNTAX

```
Get-WebConfigurationProperty -Name <String[]> [-Recurse] [-Clr <String>] [-Location <String[]>]
 [-Filter] <String[]> [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebConfigurationProperty** cmdlet gets an Internet Information Services (IIS) configuration property at the specified path.
This cmdlet is similar to the Get-WebConfiguration cmdlet, but the current cmdlet supports globbing, or wildcards.

## EXAMPLES

### Example 1: Return the default documents for the default website
```powershell
C:\PS> Get-WebConfigurationProperty -Filter "//defaultDocument/files/add" -PSPath "IIS:\Sites\Default Web Site" -Name "value" | select value
```
```output
Default.htm
Default.asp
Index.htm
Index.html
Iisstart.htm
Default.aspx
```

This command returns a list of the default documents associated with the default website.

### Example 2: Show handlers mapped to Aspnet_isapi.dll
```powershell
C:\PS> Get-WebConfigurationProperty -Filter "//handlers" -PSPath "IIS:\sites\Default Web Site" -Name Collection[scriptProcessor="*aspnet_isapi.dll"] | select path,name
```

This command gets the handlers mapped to aspnet_isapi.dll.

## PARAMETERS

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
Specifies the name of the property to get.

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

### -Recurse
Indicates that the cmdlet returns the properties of nodes contained within the hierarchy of the specified node.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PSObject

## OUTPUTS

### PSObject

## NOTES

## RELATED LINKS

[Add-WebConfigurationProperty](./Add-WebConfigurationProperty.md)

[Get-WebConfiguration](./Get-WebConfiguration.md)

[Remove-WebConfigurationProperty](./Remove-WebConfigurationProperty.md)

[Set-WebConfigurationProperty](./Set-WebConfigurationProperty.md)

