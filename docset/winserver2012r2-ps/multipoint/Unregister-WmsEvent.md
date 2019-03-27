---
external help file: WmsCmdlets.dll-Help.xml
Module Name: WmsCmdlets
online version: 
schema: 2.0.0
title: Unregister-WmsEvent
description: 
keywords: powershell, cmdlet
author: biranlic
manager: jasgro
ms.date: 2017-12-06
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 5CA610CB-38AA-408B-A4E6-C056548E100E
ms.reviewer:
ms.author: kenwith
---

# Unregister-WmsEvent

## SYNOPSIS
Unregisters for notification from Windows MultiPoint Server Core Service.

## SYNTAX

```
Unregister-WmsEvent [-TimeoutInSecond <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Unregister-WmsEvent cmdlet unregisters for notification from Windows MultiPoint Server Core Service.

## EXAMPLES

### Example
```
PS C:\> UnRegister-WmsEvent
No output.
```

This cmdlet unregisters for event notifications from Windows MultiPoint Server Core Service.

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
Describes what would happen if you executed the command without actually executing the command.

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

###  
You cannot pipe objects to Unregister-WmsEvent.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

