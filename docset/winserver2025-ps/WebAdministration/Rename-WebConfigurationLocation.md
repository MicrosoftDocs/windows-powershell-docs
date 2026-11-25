---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/rename-webconfigurationlocation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-WebConfigurationLocation
---

# Rename-WebConfigurationLocation

## SYNOPSIS
Renames a configuration location.

## SYNTAX

```
Rename-WebConfigurationLocation -Name <String> -NewName <String> [-Recurse] [[-PSPath] <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Rename-WebConfigurationLocation** cmdlet renames the specified configuration location with the new name provided.

## EXAMPLES

### Example 1: Rename a configuration location
```
IIS:\> Rename-WebConfigurationLocation -Name "Default Web Site/oldApp" -NewName "Default Web Site/newApp" -PSPath "IIS:\"
```

This command renames a configuration location on the default website from oldApp to newApp.

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
Specifies the current name of the configuration location.

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

### -NewName
Specifies the new name of the configuration location.

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

### -Recurse
Indicates that the cmdlet renames location tags defined lower in the location hierarchy.

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

[Remove-WebConfigurationLocation](./Remove-WebConfigurationLocation.md)

