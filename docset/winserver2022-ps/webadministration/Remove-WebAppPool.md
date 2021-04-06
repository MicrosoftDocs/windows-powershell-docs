---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Remove-WebAppPool
ms.reviewer:
ms.assetid: B7A73A74-B4FF-4858-A081-7DD547D5E0DD
---

# Remove-WebAppPool

## SYNOPSIS
Removes an application pool from IIS.

## SYNTAX

```
Remove-WebAppPool [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WebAppPool** cmdlet removes an application pool from Internet Information Services (IIS).

## EXAMPLES

### Example 1: Remove an application pool
```
IIS:\> New-WebAppPool -Name "MyNewAppPool" "Sleep for 5 seconds before AppPool gets removed"; Sleep 5 
IIS:\> Remove-WebAppPool -Name "MyNewAppPool"
```

This command creates a new application pool, and then removes it after waiting 5 seconds.

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

### -Name
Specifies the name of the application pool to remove.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-WebAppPool](./New-WebAppPool.md)

[Restart-WebAppPool](./Restart-WebAppPool.md)

[Start-WebAppPool](./Start-WebAppPool.md)

[Stop-WebAppPool](./Stop-WebAppPool.md)

