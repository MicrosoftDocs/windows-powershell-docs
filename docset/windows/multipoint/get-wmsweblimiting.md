---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-WmsWebLimiting
ms.reviewer:
ms.assetid: D7BCF686-38C9-47B0-B108-BEFAA9678E3B
---

# Get-WmsWebLimiting

## SYNOPSIS
Gets the web limiting configuration.

## SYNTAX

```
Get-WmsWebLimiting [-SessionId <UInt32>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WmsWebLimiting** cmdlet gets web limiting configuration, including allowed URLs, blocked URLs, and whether the system is in Allowed or Blocked mode.

## EXAMPLES

### Example 1: Get web limiting information
```
PS C:\> Get-WmsWebLimiting
Sites             IsInLimiting                IsAllowList
-----             -----------                 ----------
{test.com}        True                        False
```

This command gets web limiting information for the current computer.


## PARAMETERS

### -Server
Specifies the fully qualified host name of the MultiPoint Server that is the target of the command.
The default is localhost.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SessionId
Specifies an array of MultiPoint session IDs.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

###  
This cmdlet returns **WebLimitSetting** collection as a **PSObject** collection.

## NOTES

## RELATED LINKS

[Disable-WmsWebLimiting](./Disable-WmsWebLimiting.md)

[Enable-WmsWebLimiting](./Enable-WmsWebLimiting.md)

[Set-WmsWebLimiting](./Set-WmsWebLimiting.md)

