---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: 59C27F43-7D72-4D8C-8D4F-42ED6E220E03
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Enable-WebGlobalModule

## SYNOPSIS
Enables the specified IIS module.

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
Enables the specified IIS module.

## EXAMPLES

### -------------- EXAMPLE 1: Enable a module for a site --------------
```
IIS:\>Enable-WebGlobalModule -Name UriCacheModule -PSPath 'IIS:\sites\Default Web Site'
```

Demonstrates how to enable the module named UriCacheModule for the Default Web Site.

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
Input object that contains the module information.

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
The location in which the module is enabled.

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
The name of the module to enable.

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
This can be either an IIS configuration path in the formatcomputer name/webroot/apphost, or the IIS module path in this format IIS:\sites\Default Web Site.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-WebGlobalModule](./Disable-WebGlobalModule.md)

