---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Remove-WebConfigurationLock
ms.reviewer:
ms.assetid: 2240A329-67C4-4F6E-8C4E-F22C16D4DEB9
---

# Remove-WebConfigurationLock

## SYNOPSIS
Removes a lock on configuration settings.

## SYNTAX

```
Remove-WebConfigurationLock [-Force] [-Location <String[]>] [-Filter] <String[]> [[-PSPath] <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WebConfigurationLock** cmdlet removes a lock on configuration settings that was created by using the Add-WebConfigurationLock cmdlet.

## EXAMPLES

### Example 1: Add and remove configuration locks
```
IIS:\> Add-WebConfigurationLock -Type "general" -Filter "//asp" 
IIS:\> Remove-WebConfigurationLock -Filter "//asp" 
IIS:\> Add-WebConfigurationLock -Type "inclusive" -Filter "//asp/@lcid" 
IIS:\> Remove-WebConfigurationLock -Filter "//asp/@lcid" 
IIS:\> Add-WebConfigurationLock -Type "exclusive" -Filter "//asp/@lcid"
```

This example demonstrates how to add and remove configuration locks.

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
Forces the command to run without asking for user confirmation.

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
Specifies the location of the configuration from which this cmdlet removes the lock.

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
Specifies an IIS configuration path to the location.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WebConfigurationLock](./Add-WebConfigurationLock.md)

[Get-WebConfigurationLock](./Get-WebConfigurationLock.md)

