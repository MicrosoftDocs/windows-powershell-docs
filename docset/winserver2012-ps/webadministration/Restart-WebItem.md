---
author: Kateyanne
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
manager: dansimp
Module Name: WebAdministration
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/webadministration/restart-webitem?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Restart-WebItem

## SYNOPSIS
Restarts an application pool or a Web site.

## SYNTAX

```
Restart-WebItem [-Protocol <String>] [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
Use theRestart-WebItemcmdlets to recycle an application pool or a Web site.

## EXAMPLES

### -------------- EXAMPLE 1: Recycle an Application Pool --------------
```
IIS:\>Restart-WebItem 'IIS:\AppPools\DefaultAppPool'
```

Restarts the application pool named DefaultAppPool.

## PARAMETERS

### -PSPath
The path to the application pool or Web site.

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

### -Protocol
The protocol binding of the item to restart (applies to sites only).

```yaml
Type: String
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

### PSObject

## OUTPUTS

### PSObject

## NOTES

## RELATED LINKS

[Get-WebItemState](./Get-WebItemState.md)

[Start-WebItem](./Start-WebItem.md)

[Stop-WebItem](./Stop-WebItem.md)

