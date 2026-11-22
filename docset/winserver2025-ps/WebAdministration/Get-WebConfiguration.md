---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/get-webconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WebConfiguration
---

# Get-WebConfiguration

## SYNOPSIS
Gets an IIS configuration element.

## SYNTAX

```
Get-WebConfiguration [-Recurse] [-Metadata] [-Clr <String>] [-Location <String[]>] [-Filter] <String[]>
 [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebConfiguration** cmdlet gets the Internet Information Services (IIS) configuration element at the specified location.

## EXAMPLES

### Example 1: Query authentication settings
```
IIS:\> Get-WebConfiguration -Filter "System.WebServer/Security/Authentication/* /*" -Recurse | where {$_.enabled -eq $True} | Format-List
```

This command queries for all authentication settings specified under the default website.

## PARAMETERS

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

### -Filter
Specifies the configuration path for which this cmdlet gets the configuration elements.

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

### -Metadata
Indicates that the cmdlet returns configuration metadata such as encryption or locking settings.

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
Indicates that this cmdlet returns all elements contained in the specified location and the subsequent hierarchy.

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

[Add-WebConfiguration](./Add-WebConfiguration.md)

[Backup-WebConfiguration](./Backup-WebConfiguration.md)

[Clear-WebConfiguration](./Clear-WebConfiguration.md)

[Format-List](https://go.microsoft.com/fwlink/p/?LinkId=113302)

[Restore-WebConfiguration](./Restore-WebConfiguration.md)

[Select-WebConfiguration](./Select-WebConfiguration.md)

[Set-WebConfiguration](./Set-WebConfiguration.md)

