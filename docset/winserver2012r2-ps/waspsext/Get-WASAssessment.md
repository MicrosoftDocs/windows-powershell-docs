---
external help file: Microsoft.Assessments.WAS.PowerShell.dll-Help.xml
Module Name: WasPSExt
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/waspsext/get-wasassessment?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WASAssessment
---

# Get-WASAssessment

## SYNOPSIS
Gets a list of available assessments.

## SYNTAX

### AssessmentId
```
Get-WASAssessment [-AssessmentID] <Guid[]> [<CommonParameters>]
```

### AssessmentName
```
Get-WASAssessment [[-AssessmentName] <String[]>] [<CommonParameters>]
```

### ProgrammaticName
```
Get-WASAssessment [-ProgrammaticName] <String[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WASAssessment** cmdlet returns a list of assessments that are available on the dep_nextref_was server.
It also displays metadata, such as the GUID, the name of the assessment and the category for the assessment.
You can't modify the assessment settings in these assessments.
The list includes assessments that are predefined in the dep_nextref_wasc, or use the recommended settings.

## EXAMPLES

### Example 1: Get all assessments
```
PS C:\>Get-WASAssessment
```

This command gets all assessments registered with dep_nextref_was.

### Example 2: Get assessments by using a search string
```
PS C:\>Get-WASAssessment -AssessmentName Minifilter*
```

This command gets all assessments that have a name that starts with Minifilter.

### Example 3: Get an assessment with a specific ID
```
PS C:\>Get-WASAssessment -AssessmentId 8aa74479-d580-4d74-a4d2-f57d0f503003
```

This command gets an assessment with a specific assessment ID.

## PARAMETERS

### -AssessmentID
Specifies the GUID of the assessment you want to get.
You must specify the full GUID.
If this parameter is not specified, all assessments are listed.

```yaml
Type: Guid[]
Parameter Sets: AssessmentId
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AssessmentName
Specifies the name of the assessment you want to get.
The full name of the assessment isn't required.
Wildcards are accepted.
If this parameter is not specified, all assessments are listed.

```yaml
Type: String[]
Parameter Sets: AssessmentName
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProgrammaticName
{{Fill ProgrammaticName Description}}

```yaml
Type: String[]
Parameter Sets: ProgrammaticName
Aliases: 

Required: True
Position: 0
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

[Windows Assessment Services Technical Reference](https://go.microsoft.com/fwlink/?LinkId=215628)

[Update-WASJob](./Update-WASJob.md)

