---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: 5745A29B-5B07-4ACC-BD4D-D0DB0EF94C75
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# New-WebGlobalModule

## SYNOPSIS
Creates a new IIS global module.

## SYNTAX

```
New-WebGlobalModule [-Name] <String> [-Image <String>] [-Precondition <String>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
Creates a new IIS global module.

## EXAMPLES

### -------------- EXAMPLE 1: Adding a new module --------------
```
IIS:\>New-WebGlobalModule -Name testGlobalModule -Image c:\test\test.dll
```

Adds a new module to theglobalModuleslist.

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
The path to a DLL image (native modules only) for the new module.

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
The name of the new module.

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

