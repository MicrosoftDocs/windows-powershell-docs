---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: 188FB11F-E503-4A30-9A09-B6A89FAC54A7
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
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
Adds a new managed module to the IIS request pipeline.

## EXAMPLES

### -------------- EXAMPLE 1: Add a new managed module to the Default Web Site --------------
```
IIS:\>New-WebManagedModule -Name ContosoModule -Type Contoso.MyModule
```

The example demonstrates how to add a new module named "ContosoModule" to the Default Web Site.

## PARAMETERS

### -Force
Forces the new module to be added.

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
The location for which the new handler applies.

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
The name of the new managed module.

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
An IIS configuration path.

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
Specifies any precondition(s) of the new managed module.

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
The .NET Framework type of the new managed module.

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

