---
external help file: WmsCmdlets.dll-Help.xml
Module Name: WmsCmdlets
online version: 
schema: 2.0.0
title: Update-WmsCoreManager
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/06/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 6AA79EA1-36AB-471B-BA21-F97C845FDED3
ms.reviewer:
ms.author: v-kaunu
---

# Update-WmsCoreManager

## SYNOPSIS
Refreshes the connection with Windows MultiPoint Server Core Service.

## SYNTAX

```
Update-WmsCoreManager [-TimeoutInSecond <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Update-WmsCoreManager cmdlet refreshes the connection with Windows MultiPoint Server Core Service.

## EXAMPLES

### Example
```
PS C:\> Update-WmsCoreManager
No output.
```

This cmdlet refreshes the connection to the Windows MultiPoint Server Core Service.

### 1:
```
PS C:\>
```

## PARAMETERS

### -TimeoutInSecond
The timeout value in seconds before the operation is aborted.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

