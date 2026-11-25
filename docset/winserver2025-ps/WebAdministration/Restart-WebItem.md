---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/restart-webitem?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-WebItem
---

# Restart-WebItem

## SYNOPSIS
Restarts an application pool or a website.

## SYNTAX

```
Restart-WebItem [-Protocol <String>] [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Restart-WebItem** cmdlet restarts an application pool or a website.

## EXAMPLES

### Example 1: Restart an application pool
```
IIS:\> Restart-WebItem -PSPath 'IIS:\AppPools\DefaultAppPool'
```

This command restarts the application pool named DefaultAppPool.

## PARAMETERS

### -PSPath
Specifies the path to the application pool or web site.

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
Specifies the protocol binding of the item to restart.
This parameter applies to sites only.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PSObject

## OUTPUTS

### PSObject

## NOTES

## RELATED LINKS

[Start-WebItem](./Start-WebItem.md)

[Stop-WebItem](./Stop-WebItem.md)

