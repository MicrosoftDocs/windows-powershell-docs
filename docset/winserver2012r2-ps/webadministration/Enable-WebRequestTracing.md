---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Enable-WebRequestTracing
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 56F8DEDD-69B2-42D9-B55C-C83208EBBA8E
ms.author: v-anbarr
ms.reviewer: brianlic
---

# Enable-WebRequestTracing

## SYNOPSIS
Enables request tracing for a website.

## SYNTAX

```
Enable-WebRequestTracing [[-Name] <String>] [-Directory <String>] [-MaxLogFiles <UInt32>]
 [-MaxLogFileSize <UInt32>] [-CustomActions] [-StatusCodes <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-WebRequestTracing** cmdlet enables request tracing, and automatically configures a website rule that traces responses that have a status value between 400 and 600.

## EXAMPLES

### Example 1: Enabling request tracing for the "Default Web Site"
```
IIS:\>Enable-WebRequestTracing -Name "Default Web Site"
```

This command enables request tracing for the default website, which also automatically creates a rule that traces status code 500 errors.

## PARAMETERS

### -CustomActions
Specifies an action to take when a request tracing log file is generated.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Directory
Specifies the directory in which request tracing log files are stored.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxLogFileSize
Specifies the maximum file size of a single request tracing log file.

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

### -MaxLogFiles
Specifies the maximum number of log files to store.

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

### -Name
Specifies the name of the site for which tracing is enabled.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StatusCodes
Specifies the status codes for which a default request tracing rule is configured.
The default code value is 500.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

[Disable-WebRequestTracing](./Disable-WebRequestTracing.md)

