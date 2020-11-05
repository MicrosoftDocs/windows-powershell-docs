---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: DF86D4F3-5727-4E04-9A4C-474D8A1F66CC
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Restart-WebAppPool

## SYNOPSIS
Recycles an application pool.

## SYNTAX

```
Restart-WebAppPool [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
Causes the specified application pool to be recycled.

## EXAMPLES

### -------------- EXAMPLE 1: Recycling an Application Pool --------------
```
IIS:\>Restart-WebAppPool DefaultAppPool
```

Recycles the application pool named DefaultAppPool.

## PARAMETERS

### -Name
The name of the application pool to restart.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

