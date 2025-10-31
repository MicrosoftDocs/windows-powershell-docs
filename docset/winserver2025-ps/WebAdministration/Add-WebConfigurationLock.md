---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/add-webconfigurationlock?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WebConfigurationLock
---

# Add-WebConfigurationLock

## SYNOPSIS
Locks an IIS configuration section or element.

## SYNTAX

```
Add-WebConfigurationLock -Type <String> [-Force] [-Passthru] [-Location <String[]>] [-Filter] <String[]>
 [[-PSPath] <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-WebConfigurationLock** cmdlet locks an Internet Information Services (IIS) configuration section, element, or attribute.

## EXAMPLES

### Example 1: Add and remove configuration locks
```
IIS:\> Add-WebConfigurationLock -Type "general" -Filter "//asp"
IIS:\> Remove-WebConfigurationLock -Filter "//asp"
IIS:\> Add-WebConfigurationLock -Type "inclusive" -Filter "//asp/@lcid"
IIS:\> Remove-WebConfigurationLock -Filter "//asp/@lcid"
IIS:\> Add-WebConfigurationLock -Type "exclusive" -Filter "//asp/@lcid"
```

This example demonstrates how to add and remove inclusive and exclusive locks using a filter.

## PARAMETERS

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
Specifies an XPath filter expression.

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
Forces the configuration lock.

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
Specifies the location at which this cmdlet applies the configuration lock.

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

### -Passthru
Passes an object that represents the configuration lock to the pipeline.

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

### -Type
Specifies the type of configuration lock that this cmdlet adds.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WebConfigurationLock](./Get-WebConfigurationLock.md)

[Remove-WebConfigurationLock](./Remove-WebConfigurationLock.md)

