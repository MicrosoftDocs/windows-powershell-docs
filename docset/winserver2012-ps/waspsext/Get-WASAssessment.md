---
author: Kateyanne
external help file: WasPsExt_Cmdlets.xml
manager: dansimp
Module Name: WasPSExt
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/waspsext/get-wasassessment?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WASAssessment

## SYNOPSIS
Gets a list of available assessments.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-WASAssessment [-AssessmentID] <Guid[]>
```

### UNNAMED_PARAMETER_SET_2
```
Get-WASAssessment [[-AssessmentName] <String[]>]
```

## DESCRIPTION
The **Get-WASAssessment** cmdlet returns a list of assessments that are available on the Windows Assessment Services server.
It also displays metadata, such as the GUID, the name of the assessment and the category for the assessment.
You can't modify the assessment settings in these assessments.
The list includes assessments that are predefined in the Windows ASC, or use the recommended settings.

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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Windows Assessment Services Technical Reference](https://go.microsoft.com/fwlink/?LinkId=215628)

[Update-WASJob](./Update-WASJob.md)

