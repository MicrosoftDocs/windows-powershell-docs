---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
ms.date: 09/27/2022
online version: https://learn.microsoft.com/powershell/module/clusterawareupdating/get-caureport?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CauReport
---

# Get-CauReport

## SYNOPSIS
Gets the Updating Run reports for all known Updating Runs, or all Updating Runs that match the
specified dates or other specified parameters.

## SYNTAX

### AllParamsSet (Default)

```
Get-CauReport [[-ClusterName] <String>] [-Detailed] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### RangeParamSet

```
Get-CauReport [[-ClusterName] <String>] [[-StartDate] <DateTime>] [[-EndDate] <DateTime>]
 [-Detailed] [-Credential <PSCredential>] [<CommonParameters>]
```

### LastParamSet

```
Get-CauReport [[-ClusterName] <String>] [-Last] [-Detailed] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### SpecificReportParamSet

```
Get-CauReport [[-ClusterName] <String>] [-Report <CauReportSummary>]
 [-Credential <PSCredential>]  [<CommonParameters>]
```

## DESCRIPTION

The `Get-CauReport` cmdlet gets the Updating Run reports for all known Updating Runs, or all
Updating Runs that match the specified dates or other specified parameters. This cmdlet can return a
list of all Updating Run reports between the specified **StartDate** and **EndDate** parameters, or
if the **Last** parameter is specified instead of dates, then the cmdlet returns the most recent
Updating Run report. By default, the report contains summaries only, but more detail can be obtained
with the **Detailed** parameter or by using the **Report** parameter and specifying a Cluster-Aware
Updating (CAU) report summary object.

## EXAMPLES

### Example 1: Get a detailed list of updating runs from the specified cluster

```powershell
Get-CauReport -ClusterName Contoso-FC1 -StartDate 01/01/2012 -Detailed
```

This command gets a detailed list of the updating runs performed on the cluster named **Contoso-FC1**
on 01/01/2012 or later.

### Example 2: Get a detailed list of updating runs from a date span from the specified cluster

```powershell
Get-CauReport -ClusterName "Contoso-FC1" -StartDate 01/01/2012 -EndDate 04/01/2012 -Detailed
```

This command gets a detailed list of the updating runs performed on the cluster called **Contoso-FC1**
starting with updating runs on 01/01/2012 and ending with updating runs on 04/01/2012.

### Example 3: Get the last updating run summary from the specified cluster

```powershell
$CauReportSummary = Get-CauReport "Contoso-FC1" -Last
Get-CauReport "Contoso-FC1" -Report $CauReportSummary
```

The first command gets the last updating run report summary from the cluster named **Contoso-FC1** and
stores the result in the variable named `$CauReportSummary`.

The second command gets the detailed report from the information stored in the `$CauReportSummary`
variable.

## PARAMETERS

### -ClusterName

Specifies the name of the cluster for which this cmdlet gets reports. This parameter is only
required when this cmdlet isn't run on a failover cluster node, or this cmdlet is used to reference
a failover cluster different from where the cmdlet is run.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies the administrative credentials for the target cluster.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Detailed

Specifies that cmdlet gets full results for one or more runs, instead of just summary information.

```yaml
Type: SwitchParameter
Parameter Sets: AllParamsSet, RangeParamSet, LastParamSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndDate

Specifies that this cmdlet gets only the reports for runs before this time.

```yaml
Type: DateTime
Parameter Sets: RangeParamSet
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Last

Indicates that this cmdlet gets only the most recent run report.

```yaml
Type: SwitchParameter
Parameter Sets: LastParamSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Report

Specifies the report summary that this cmdlet gets detailed results for the run.

```yaml
Type: CauReportSummary
Parameter Sets: SpecificReportParamSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StartDate

Specifies that this cmdlet gets only the reports for runs after this time.

```yaml
Type: DateTime
Parameter Sets: RangeParamSet
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### Microsoft.ClusterAwareUpdating.CauReportSummary

## OUTPUTS

### Microsoft.ClusterAwareUpdating.CauReport

### Microsoft.ClusterAwareUpdating.CauReportSummary

## NOTES

## RELATED LINKS

[Export-CauReport](export-caureport.md)
