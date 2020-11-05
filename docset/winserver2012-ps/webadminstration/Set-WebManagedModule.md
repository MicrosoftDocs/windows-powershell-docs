---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: DDF01729-FDE2-427F-AE88-C6F4AE80F70A
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-WebManagedModule

## SYNOPSIS
Configures an IIS managed module.

## SYNTAX

```
Set-WebManagedModule [-Name] <String> [-Type <String>] [-Precondition <String>] [-Location <String[]>]
 [[-PSPath] <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Configures an IIS managed module.

## EXAMPLES

### -------------- EXAMPLE 1: Change a property of a managed module --------------
```
IIS:\>Set-WebManagedModule -Name UrlMappingsModule -Type Test.Test
```

Changes the type of the module named UrlMappingsModule.

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

### -Location
Location on which to set the configuration.

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
Name of the managed module to configure.

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
An IIS configuration path to the module.

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
Preconditions of the module.

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
The managed type of the module.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

