---
author: Kateyanne
description: 
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
manager: jasgro
Module Name: WebAdministration
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/webadministration/restart-webapppool?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-WebAppPool
---

# Restart-WebAppPool

## SYNOPSIS
Restarts an application pool.

## SYNTAX

```
Restart-WebAppPool [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Restart-WebAppPool** cmdlet restarts the specified application pool.

## EXAMPLES

### Example 1: Restart an application pool
```
IIS:\>Restart-WebAppPool -Name "DefaultAppPool"
```

This command restarts the application pool named DefaultAppPool.

## PARAMETERS

### -Name
Specifies the name of the application pool to restart.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-WebAppPool](./New-WebAppPool.md)

[Remove-WebAppPool](./Remove-WebAppPool.md)

[Start-WebAppPool](./Start-WebAppPool.md)

[Stop-WebAppPool](./Stop-WebAppPool.md)

