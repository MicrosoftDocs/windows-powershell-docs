---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: brianlic
author: brianlic-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: processmitigations.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2017-03-29
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: ConvertTo-ProcessMitigationPolicy
---

# ConvertTo-ProcessMitigationPolicy

## SYNOPSIS
Converts an mitigation policy file formats.

## SYNTAX

```
ConvertTo-ProcessMitigationPolicy [-EMETFile <String>] [-Output <String>] [<CommonParameters>]
```

## DESCRIPTION
Converts an EMET policy file or pinning rule file to a new Windows 10 format.

## EXAMPLES

### Example 1
```
PS C:\> ConvertTo-ProcessMitigationPolicy -EMETFile policy.xml -Output result.xml
```

Converts EMET file policy.xml to result.xml, may also generate a CI file CI-result.xml if necessary.

## PARAMETERS

### -EMETFile
EMET File or Pinning Rule File to convert.

```yaml
Type: String
Parameter Sets: (All)
Aliases: f

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Output
File to save the output to.
May also create a "CI-"\`output.xml\` file if necessary

```yaml
Type: String
Parameter Sets: (All)
Aliases: o

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

### System.Object

## NOTES

## RELATED LINKS

