---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: 8E74C047-54C0-4736-8145-54E6B7201EA8
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-WebHandler

## SYNOPSIS
Gets IIS request handlers.

## SYNTAX

```
Get-WebHandler [[-Name] <String>] [-Location <String[]>] [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
Gets IIS request handlers.
If the Name parameter is used, information is returned for the specified handler.

## EXAMPLES

### -------------- EXAMPLE 1: Get the handler section --------------
```
IIS:\>Get-WebHandler -PSPath 'IIS:\Sites\Default Web Site'
```

Gets handlers configured for the Default Web Site.

## PARAMETERS

### -Location
Specifies the location for which the cmdlet returns handler information.

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
The name of a handler to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

