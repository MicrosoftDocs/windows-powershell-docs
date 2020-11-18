---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Remove-WebConfigurationLocation
ms.reviewer:
ms.assetid: 859BCA01-DD47-4DD2-A8A9-E32D648C648E
---

# Remove-WebConfigurationLocation

## SYNOPSIS
Removes an IIS configuration location.

## SYNTAX

```
Remove-WebConfigurationLocation [[-Name] <String>] [-Recurse] [[-PSPath] <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WebConfigurationLocation** cmdlet removes an Internet Information Services (IIS) configuration location.

## EXAMPLES

### Example 1: Add and remove a configuration location
```
IIS:\> Set-WebConfigurationProperty -PSPath "IIS:\" -Filter "//windowsAuthentication" -Location "Default Web Site/mypage.htm" -Name "enabled" -Value $True 
IIS:\> Get-WebConfigurationLocation -Name "Default Web Site" -PSPath "IIS:\" "Sleep 5 seconds before removing the configuration location"; Sleep 5 
IIS:\> Remove-WebConfigurationLocation -Name "Default Web Site/my*" 
IIS:\> Get-WebConfigurationLocation -Name "Default Web Site" -PSPath "IIS:\"
```

This example adds, and then removes, a configuration location.

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

### -Name
Specifies the name of the configuration location that this cmdlet removes.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PSPath
Specifies an IIS configuration path.

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
Indicates that this cmdlet removes locations within the hierarchy of the specified location.

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

[Get-WebConfigurationLocation](./Get-WebConfigurationLocation.md)

[Rename-WebConfigurationLocation](./Rename-WebConfigurationLocation.md)

