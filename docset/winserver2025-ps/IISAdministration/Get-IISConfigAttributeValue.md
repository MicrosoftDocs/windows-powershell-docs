---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/get-iisconfigattributevalue?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IISConfigAttributeValue
---

# Get-IISConfigAttributeValue

## SYNOPSIS
Gets a configuration attribute value from an IIS configuration section or configuration element attribute.

## SYNTAX

```
Get-IISConfigAttributeValue [-ConfigElement] <ConfigurationElement> [-AttributeName] <String>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-IISConfigAttributeValue** cmdlet gets a configuration attribute value from an Internet Information Services (IIS) configuration section attribute or a configuration element attribute.
The value returned is the value that can be extracted from the given **ConfigurationElement** and not necessarily the effective value for a given site / virtual directory / folder etc.
To obtain the effective attribute values, always retrieve the configuration element by specifying the commit path as the deepest level possible.
Even the configuration attribute is not defined at that level, the parent attributes are scanned and the effective configuration element is returned.
You can then work on this **ConfigurationElement** to get/set/remove configuration attribute values.

## EXAMPLES

### Example 1: Get a configuration attribute from an IIS website
```
PS C:\> Get-IISSite "Default Web Site" | Get-IISConfigElement -ChildElementName "limits" | Get-IISConfigAttributeValue -AttributeName "MaxUrlSegments"
```

This command gets the configuration attribute MaxUrlSegments for the Default Web Site.

### Example 2: Get configuration attribute values from different parts of the configuration store
```
PS C:\> Get-IISConfigSection "system.webServer/asp" | Get-IISConfigAttributeValue -AttributeName "ScriptErrorMessage"
An error occurred on the server when processing the URL. Please contact the system administrator. <p/> If you are the system administrator please click <a href="https://go.microsoft.com/fwlink/?LinkID=82731">here</a> to find out more about this error.
```

This command gets the global attribute value for ScriptErrorMessage

## PARAMETERS

### -AttributeName
Specifies the name of the attribute that will be retrieved.

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
Specifies the IIS ConfigurationSection or ConfigurationElement for which the attribute value will be looked up.

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

[Set-IISConfigAttributeValue](./Set-IISConfigAttributeValue.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

