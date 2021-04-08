---
author: Kateyanne
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
manager: dansimp
Module Name: WebAdministration
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/webadministration/restart-webapppool?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
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

