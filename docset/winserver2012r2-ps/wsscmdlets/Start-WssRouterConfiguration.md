---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Start-WssRouterConfiguration
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: FD92EDE0-1DDD-4BF9-A7F9-89A8BF8BFDE6
ms.author: v-anbarr
ms.reviewer: brianlic
---

# Start-WssRouterConfiguration

## SYNOPSIS
Configures port forwarding for routers.

## SYNTAX

```
Start-WssRouterConfiguration [-Manual] [<CommonParameters>]
```

## DESCRIPTION
The **Start-WssRouterConfiguration** cmdlet configures port forwarding for UPnP-enabled routers.

## EXAMPLES

### Example 1: Start router configuration
```
PS C:\> Start-WssRouterConfiguration
```

This command starts automatic router configuration.

### Example 2: Specify manual router configuration
```
PS C:\> Start-WssRouterConfiguration -Manual
```

This command skips automatic router configuration.
The command specifies the **Manual** parameter to inform wseblue_2 that the router is manually configured.

### 1:
```
PS C:\>
```

## PARAMETERS

### -Manual
Indicates to wseblue_1 that router configuration was intentionally skipped.
If you plan to manually configure the router, specify this parameter.

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

[Repair-WssRouterConfiguration](./Repair-WssRouterConfiguration.md)

