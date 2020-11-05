---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: New-WebGlobalModule
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 5745A29B-5B07-4ACC-BD4D-D0DB0EF94C75
ms.author: v-kaunu
ms.reviewer: brianlic
---

# New-WebGlobalModule

## SYNOPSIS
Creates an IIS global module.

## SYNTAX

```
New-WebGlobalModule [-Name] <String> [-Image <String>] [-Precondition <String>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **New-WebGlobalModule** cmdlet creates an Internet Information Services (IIS) global module.

## EXAMPLES

### Example 1: Adding a new module
```
IIS:\>New-WebGlobalModule -Name "testGlobalModule" -Image "c:\test\test.dll"
```

This command adds a new module to the global Modules list.

## PARAMETERS

### -Force
Forces the creation of the new module.

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

### -Image
Specifies the path to a DLL image file (native modules only) for the new module.

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

### -Name
Specifies the name of the new module.

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

### -Precondition
Specifies any preconditions to be used for the new module.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-WebGlobalModule](./Disable-WebGlobalModule.md)

[Enable-WebGlobalModule](./Enable-WebGlobalModule.md)

[Get-WebGlobalModule](./Get-WebGlobalModule.md)

[Remove-WebGlobalModule](./Remove-WebGlobalModule.md)

[Set-WebGlobalModule](./Set-WebGlobalModule.md)

