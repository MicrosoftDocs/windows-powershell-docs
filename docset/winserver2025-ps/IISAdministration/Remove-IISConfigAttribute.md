---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/remove-iisconfigattribute?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-IISConfigAttribute
---

# Remove-IISConfigAttribute

## SYNOPSIS
Removes a configuration attribute from an IIS configuration section or configuration element attribute.

## SYNTAX

```
Remove-IISConfigAttribute [-ConfigElement] <ConfigurationElement> [-AttributeName] <String>
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-IISConfigAttribute** cmdlet removes a configuration attribute from an Internet Information Services (IIS) configuration section or a configuration element.
The value removed is the value for the given ConfigurationElement and not necessarily the effective value for a given site / virtual directory / folder etc.
To obtain the effective attribute values, always retrieve the configuration element by specifying the commit path as the deepest level possible.
Even the configuration attribute is not defined at that level, the parent attributes are scanned and the effective configuration element is returned.
You can then work on this ConfigurationElement to get/set/remove configuration attribute values.

## EXAMPLES

### Example 1: Remove a configuration attribute from an IIS web site.
```
PS C:\> Get-IISSite "Default Web Site" | Get-IISConfigElement -ChildElementName "limits" | Remove-IISConfigAttribute -AttributeName "MaxUrlSegments"
```

This command removes the configuration attribute value for the attribute MaxUrlSegments from the Default Web Site, defaulting to its parent or system wide defaults.

### Example 2: Remove configuration attribute values from different parts of the configuration store:
```
PS C:\> Get-IISConfigSection "system.webServer/asp" | Remove-IISConfigAttribute -AttributeName "ScriptErrorMessage"
```

This command removes the global attribute value for ScriptErrorMessage, defaulting to the schema default.

## PARAMETERS

### -AttributeName
Specifies the name of the attribute that is to be deleted.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigElement
Specifies the IIS ConfigurationSection or ConfigurationElement from which the matching attribute is to be deleted.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Web.Administration.ConfigurationElement

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-IISConfigAttributeValue](./Get-IISConfigAttributeValue.md)

[Set-IISConfigAttributeValue](./Set-IISConfigAttributeValue.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

