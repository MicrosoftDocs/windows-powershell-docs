---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Repair-WssAlert
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: EB85F576-0780-4BA6-A1C8-E738BC032732
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Repair-WssAlert

## SYNOPSIS
Repairs an alert.

## SYNTAX

### NameSet (Default)
```
Repair-WssAlert [-FeatureName] <String> [-HealthDefinitionName] <String> [[-MachineName] <String>]
 [<CommonParameters>]
```

### AlertSet
```
Repair-WssAlert [-Alert] <Alert> [<CommonParameters>]
```

## DESCRIPTION
The **Repair-WssAlert** cmdlet runs the repair task for an alert.
Specify an alert object or specify the feature and health definition file associated with the alert.

## EXAMPLES

### Example 1: Repair an alert
```
PS C:\> Repair-WssAlert -FeatureName "MicrosoftServicing" -HealthDefinitionName "MUOptIn"
```

This command runs the repair task for the alert associated with the feature named MicrosoftServicing and the health definition named MUOptIn.

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
Specifies the name of the computer on which the server generated the alert.

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

### Microsoft.WindowsServerSolutions.NetworkHealth.AlertFramework.Alert

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssAlert](./Get-WssAlert.md)

[Enable-WssAlert](./Enable-WssAlert.md)

[Disable-WssAlert](./Disable-WssAlert.md)

[Clear-WssAlert](./Clear-WssAlert.md)

