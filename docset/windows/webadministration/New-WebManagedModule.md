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
title: New-WebManagedModule
ms.reviewer:
ms.assetid: 188FB11F-E503-4A30-9A09-B6A89FAC54A7
---

# New-WebManagedModule

## SYNOPSIS
Adds a new managed module to the IIS request pipeline.

## SYNTAX

```
New-WebManagedModule [-Name] <String> [-Type <String>] [-Precondition <String>] [-Force] [-Location <String[]>]
 [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **New-WebManagedModule** cmdlet adds a new managed module to the Internet Information Services (IIS) request pipeline.

## EXAMPLES

### Example 1: Add a new managed module to the default website
```
IIS:\> New-WebManagedModule -Name "ContosoModule" -Type "Contoso.MyModule"
```

This command adds a new module named ContosoModule to the default website.

## PARAMETERS

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
Specifies the location for which the new handler applies.

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
Specifies the name of the new managed module.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

### -Precondition
Specifies any preconditions for the new managed module.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Type
Specifies the .NET Framework type of the new managed module.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WebManagedModule](./Get-WebManagedModule.md)

[Remove-WebManagedModule](./Remove-WebManagedModule.md)

[Set-WebManagedModule](./Set-WebManagedModule.md)

