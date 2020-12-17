---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: B7A73A74-B4FF-4858-A081-7DD547D5E0DD
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Remove-WebAppPool

## SYNOPSIS
Removes an application pool from IIS.

## SYNTAX

```
Remove-WebAppPool [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Removes an application pool from IIS.

## EXAMPLES

### -------------- EXAMPLE 1: Removing an Application Pool --------------
```
IIS:\>New-WebAppPool MyNewAppPool "Sleep for 5 seconds before AppPool gets removed"; Sleep 5 Remove-WebAppPool MyNewAppPool
```

This example demonstrates how to create a new application pool, and then removes it after waiting 5 seconds.

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
The name of the application pool to remove.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

