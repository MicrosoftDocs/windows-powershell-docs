---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: 3F5C852A-05EE-454C-8333-7479931BE260
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Remove-WebHandler

## SYNOPSIS
Removes a request handler from IIS.

## SYNTAX

```
Remove-WebHandler [-Name] <String> [-Location <String[]>] [[-PSPath] <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Removes a request handler from IIS.

## EXAMPLES

### -------------- EXAMPLE 1: Remove a handler --------------
```
IIS:\>Remove-WebHandler -Name testHandler -PSPath "IIS:\sites\Default Web Site"
```

Removes the request handler named testHandler from the Default Web Site.

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
The configuration location from which the handler is removed.

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
The name of the handler to remove.

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
An IIS configuration path to the location.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

