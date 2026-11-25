---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.BestPractices.Cmdlets.dll-Help.xml
Module Name: BestPractices
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/bestpractices/set-bparesult?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-BpaResult
---

# Set-BpaResult

## SYNOPSIS
Excludes or includes existing results of a BPA scan to display only the specified scan results.

## SYNTAX

```
Set-BpaResult [[-Exclude] <Boolean>]
 [-Results] <System.Collections.Generic.List`1[Microsoft.BestPractices.CoreInterface.Result]>
 [[-RepositoryPath] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-BPAResult** cmdlet excludes or includes existing results of a Best Practices Analyzer (BPA) scan to display only the specified scan results.
The action specified in this cmdlet (such as **Exclude**) determines how the existing results of a BPA scan are updated.
This cmdlet is typically applied after using the **Get-BpaResult** cmdlet to return a collection of scan results.
Filters can be applied to results returned by the **Get-BpaResult** cmdlet, and then pipe the filtered collection of results to this cmdlet, specifying either to include or exclude filtered scan results.

This will update the results in the result file with the specified result collection with the action specified.
The administrator would generally need to call the **Get-BpaResult** cmdlet before this to get the result collection, apply some filters and pipe the collection to this cmdlet specifying the action (exclusion or inclusion).

If this cmdlet is canceled before the results are written to a file, then the operation is canceled and the results file is not modified.
If cancellation occurs after the results file has been modified, then the actions of the cmdlet are carried out, and the cmdlet cannot be canceled.

## EXAMPLES

### Example 1: Exclude filtered results from a BPA scan
```
PS C:\> Get-BPAResult -ModelId "ModelId1" | Where-Object -FilterScript { $_.Category -Eq "Performance" } | Set-BPAResult -ModelId "ModelId1" -Exclude $True
```

This example, to the left of the first pipeline operator (`|`), uses the **Get-BpaResult** cmdlet to retrieve BPA scan results for the model ID represented by ModelId1.
The second section of the cmdlet filters the results of **Get-BpaResult** to get only those scan results for which the category name is equal to Performance.
The final section of the example, following the second pipeline operator, excludes the Performance results filtered by the previous section of the example.

### Example 2: Use a variable to exclude filtered results from a BPA scan
```
The $rcPolicy variable is created to store the filtered results of **Get-BpaResult**; this variable can be used in subsequent cmdlets to represent those results.
PS C:\> $rcPolicy = Get-BPAResult -ModelId ModelId1 | Where-Object -FilterScript { $_.Category -Eq "Policy" }

The second line of the example uses this cmdlet to exclude the set of results stored in the $rcPolicy variable, for the specified model ID. In this cmdlet, the *Results* parameter is added because the administrator wants to exclude a specific subset of scan results for that model, and has created the variable $rcPolicy to represent that subset of results.
PS C:\> Set-BPAResult -ModelId "ModelId1" -Exclude $True -Results $rcPolicy
```

This example, to the left of the pipeline operator (`|`), instructs the **Get-BpaResult** cmdlet to retrieve BPA scan results for the model represented by ModelId1.
The second section of the example, after the pipeline, filters the results of **Get-BpaResult** to return only those scan results for which the category name is equal to (note the Eq comparison operator) Policy.

## PARAMETERS

### -Exclude
Removes any BPA scan results that are specified by a filter added to this cmdlet.
The Exclude action applies to all results returned by this cmdlet.
To exclude results by using this parameter, add the value `$True` following the parameter, as shown:`-Exclude $True`

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RepositoryPath
Specifies the location where the report should be stored.
The **Invoke-BpaModel** cmdlet provides an option to store the results either in the default reports repository location referred by ReportsRoot registry key or in a custom location supplied as input to this parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Results
Specifies the result collection to be updated in the result file returned by this cmdlet.
This parameter is typically used to specify a filtered subset of scan results that has already been stored in a variable; the variable name is provided as the valid value for this parameter.
This is the result collection which needs to be updated in the result file.
For example, if a variable named $allPerformance is created to store all the Performance category results for a BPA scan of all roles on a computer, and to exclude those Performance results from the complete collection of scan results, add the following parameter to this cmdlet: `-Results $allPerformance`

```yaml
Type: System.Collections.Generic.List`1[Microsoft.BestPractices.CoreInterface.Result]
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Collections.Generic.List<Microsoft.BestPractices.CoreInterface.Result>
The input object specified by the *Results* parameter.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-BpaModel](./Get-BpaModel.md)

[Get-BpaResult](./Get-BpaResult.md)

[Invoke-BpaModel](./Invoke-BpaModel.md)

[Where-Object](https://go.microsoft.com/fwlink/?LinkID=113423)

