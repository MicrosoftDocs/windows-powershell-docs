---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ProcessMitigations.Commands.dll-Help.xml
Module Name: ProcessMitigations
ms.date: 03/29/2017
online version: https://learn.microsoft.com/powershell/module/processmitigations/convertto-processmitigationpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-ProcessMitigationPolicy
---

# ConvertTo-ProcessMitigationPolicy

## SYNOPSIS
Converts an mitigation policy file formats.

## SYNTAX

```
ConvertTo-ProcessMitigationPolicy [-EMETFilePath] <String> [-OutputFilePath] <String> [<CommonParameters>]
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
Specifies the full path of the Enhanced Mitigation Experience Tool (EMET) file to convert.

```yaml
Type: String
Parameter Sets: (All)
Aliases: f

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -OutputFilePath
Specifies the full path of the converted format file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: o

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

