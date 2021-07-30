---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ProcessMitigations.dll-Help.xml
Module Name: ProcessMitigations
ms.date: 03/29/2017
online version: https://docs.microsoft.com/powershell/module/processmitigations/convertto-processmitigationpolicy?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-ProcessMitigationPolicy
---

# ConvertTo-ProcessMitigationPolicy

## SYNOPSIS
Converts an mitigation policy file formats.

## SYNTAX

```
ConvertTo-ProcessMitigationPolicy -EMETFilePath <String> -OutputFilePath <String> [<CommonParameters>]
```

## DESCRIPTION
Converts an EMET policy file or pinning rule file to a new Windows 10 format.

## EXAMPLES

### Example 1
```
PS C:\> ConvertTo-ProcessMitigationPolicy -EMETFilePath policy.xml -OutputFilePath result.xml
```

Converts EMET file policy.xml to result.xml, may also generate a CI file CI-result.xml if necessary.

## PARAMETERS

### -EMETFilePath
{{Fill EMETFilePath Description}}```yaml
Type: String
Parameter Sets: (All)
Aliases: f

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -OutputFilePath
{{Fill OutputFilePath Description}}```yaml
Type: String
Parameter Sets: (All)
Aliases: o

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

