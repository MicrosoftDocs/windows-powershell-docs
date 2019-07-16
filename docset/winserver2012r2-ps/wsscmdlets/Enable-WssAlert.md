---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Enable-WssAlert
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 18DC4007-1043-48D5-B6A1-68D74F97C0E6
ms.author: v-anbarr
ms.reviewer: brianlic
---

# Enable-WssAlert

## SYNOPSIS
Enables an alert.

## SYNTAX

### NameSet (Default)
```
Enable-WssAlert [-FeatureName] <String> [-HealthDefinitionName] <String> [[-MachineName] <String>]
 [<CommonParameters>]
```

### AlertSet
```
Enable-WssAlert [-Alert] <Alert> [<CommonParameters>]
```

## DESCRIPTION
The **Enable-WssAlert** cmdlet enables an alert that you have disabled or ignored.
Specify an alert object or specify the feature and health definition file associated with an alert.

## EXAMPLES

### Example 1: Enable an alert
```
PS C:\> Enable-WssAlert -FeatureName "MicrosoftServicing" -HealthDefinitionName "MUOptIn"
```

This command enables the alert associated with the feature named MicrosoftServicing and the health definition named MUOptIn.

## PARAMETERS

### -Alert
Specifies a **WssAlert** object.
To obtain a **WssAlert** object, use the Get-WssAlert cmdlet.

```yaml
Type: Alert
Parameter Sets: AlertSet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -FeatureName
Specifies the name of the feature associated with the alert.

```yaml
Type: String
Parameter Sets: NameSet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HealthDefinitionName
Specifies the name of the health definition associated with the alert.

```yaml
Type: String
Parameter Sets: NameSet
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MachineName
Specifies the name of a computer.

```yaml
Type: String
Parameter Sets: NameSet
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String,System.String

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssAlert](./Get-WssAlert.md)

[Disable-WssAlert](./Disable-WssAlert.md)

[Clear-WssAlert](./Clear-WssAlert.md)

[Repair-WssAlert](./Repair-WssAlert.md)

