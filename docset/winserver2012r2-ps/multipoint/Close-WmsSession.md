---
external help file: WmsCmdlets.dll-Help.xml
Module Name: WmsCmdlets
online version: 
schema: 2.0.0
title: Close-WmsSession
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/06/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 299D02FC-4C37-44F9-863D-E2880EA533A3
ms.reviewer:
ms.author: v-kaunu
---

# Close-WmsSession

## SYNOPSIS
Logs the user off the specified session.

## SYNTAX

```
Close-WmsSession -SessionId <Int32> [-TimeoutInSecond <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Close-WmsSession cmdlet logs off the user for the specified session.

## EXAMPLES

### Example
```
PS C:\> Close-WmsSession -SessionId 3
No output.
```

RDS session with Session ID #3 will be logged out.

### 1:
```
PS C:\>
```

## PARAMETERS

### -SessionId
Specifies a Remote Desktop Session (RDS) using SessionID.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

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
Returns ItemNotFoundException if the specified session ID is not found.

## NOTES

## RELATED LINKS

