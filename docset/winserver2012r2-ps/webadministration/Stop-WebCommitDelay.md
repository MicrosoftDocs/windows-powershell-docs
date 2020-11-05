---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Stop-WebCommitDelay
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 5E131CE9-F931-49B5-96E2-19D92CC2A54E
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Stop-WebCommitDelay

## SYNOPSIS
Instructs the IIS configuration system to resume the commitment of changes.

## SYNTAX

```
Stop-WebCommitDelay [[-Commit] <Boolean>] [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-WebCommitDelay** cmdlet instructs the Internet Information Services (IIS) configuration system to end the delay of commitment changes started by the Start-WebCommitDelay cmdlet.
You can choose to either commit or discard configuration changes made by using the **Commit** parameter.

## EXAMPLES

### Example 1: Commit configuration changes
```
PS C:\>Stop-WebCommitDelay -Commit $True
```

This command commits the configuration changes made since the Start-WebCommitDelay cmdlet was run.

### Example 2: Discard configuration changes
```
PS C:\>Stop-WebCommitDelay -Commit $False
```

This command discards the configuration changes made since the Start-WebCommitDelay cmdlet was run.

## PARAMETERS

### -Commit
Indicates whether the IIS configuration system should commit changes when the value is $True or to discard changes when to the value is $False.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PSPath
Specifies the configuration path.
This can be either an IIS configuration path in the format Computer name/webroot/apphost, or the IIS module path in this format IIS:\sites\Default Web Site.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Start-WebCommitDelay](./Start-WebCommitDelay.md)

