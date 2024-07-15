---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/enable-webglobalmodule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WebGlobalModule
---

# Enable-WebGlobalModule

## SYNOPSIS
Enables an IIS module.

## SYNTAX

### InputProperties (Default)
```
Enable-WebGlobalModule [-Name] <String> [-Type <String>] [-Precondition <String>] [-Force]
 [-Location <String[]>] [[-PSPath] <String[]>] [<CommonParameters>]
```

### InputObject
```
Enable-WebGlobalModule -InputObject <PSObject> [-Force] [-Location <String[]>] [[-PSPath] <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Enable-WebGlobalModule** cmdlet enables the specified Internet Information Services (IIS) module.

## EXAMPLES

### Example 1: Enable a module for a site
```
IIS:\> Enable-WebGlobalModule -Name "UriCacheModule" -PSPath "IIS:\sites\Default Web Site"
```

This command enables the module named UriCacheModule for the default website.

## PARAMETERS

### -Force
Forces the module to be enabled.

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
Specifies an input object that contains the module information.

```yaml
Type: PSObject
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Location
Specifies the location in which this cmdlet enables the module.

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
Specifies the name of the module to enable.

```yaml
Type: String
Parameter Sets: InputProperties
Aliases:

Required: True
Position: 0
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

### -Precondition
Specifies a precondition for the module.

```yaml
Type: String
Parameter Sets: InputProperties
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Type
Specifies the managed type of the module.

```yaml
Type: String
Parameter Sets: InputProperties
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-WebGlobalModule](./Disable-WebGlobalModule.md)

[Get-WebGlobalModule](./Get-WebGlobalModule.md)

[New-WebGlobalModule](./New-WebGlobalModule.md)

[Remove-WebGlobalModule](./Remove-WebGlobalModule.md)

[Set-WebGlobalModule](./Set-WebGlobalModule.md)

