---
author: Kateyanne
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
manager: dansimp
Module Name: WebAdministration
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/webadministration/start-webapppool?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Start-WebAppPool

## SYNOPSIS
Starts an application pool.

## SYNTAX

```
Start-WebAppPool [[-Name] <String>] [-Passthru] [<CommonParameters>]
```

## DESCRIPTION
Starts the specified application pool.

## EXAMPLES

### -------------- EXAMPLE 1: Starting an Application Pool --------------
```
IIS:\>Start-WebAppPool -Name "DefaultAppPool"
```

Starts the application pool named DefaultAppPool.

### -------------- EXAMPLE 2: Starting stopped Application Pools --------------
```
IIS:\>Get-ChildItem IIS:\AppPools | where {$_.state -eq "Stopped"} | Start-WebAppPool
```

Starts the application pools that are currently stopped.

## PARAMETERS

### -Name
The name of the application pool to start.

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

### -Passthru
Passes an object that represents the application pool to the pipeline.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

