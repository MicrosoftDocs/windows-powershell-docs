---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Repair-WssRemoteWebAccess
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 774509E5-6635-4381-80D6-4FD9E7B221BA
ms.author: kenwith
ms.reviewer: brianlic
---

# Repair-WssRemoteWebAccess

## SYNOPSIS
Repairs Remote Web Access.

## SYNTAX

```
Repair-WssRemoteWebAccess [-SkipRouter] [<CommonParameters>]
```

## DESCRIPTION
The **Repair-WssRemoteWebAccess** cmdlet repairs Remote Web Access in a sbs_sbs8_2 installation.
The cmdlet initializes and starts the service.

## EXAMPLES

### Example 1: Repair Remote Web Access
```
PS C:\> Repair-WssRemoteWebAccess -SkipRouter
```

This command repairs Remote Web Access but skips the router configuration task.

## PARAMETERS

### -SkipRouter
Indicates that the cmdlet skips the router configuration task.
If you want to manually configure the router, set this parameter to $True

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

[Disable-WssRemoteWebAccess](./Disable-WssRemoteWebAccess.md)

[Enable-WssRemoteWebAccess](./Enable-WssRemoteWebAccess.md)

