---
author: Kateyanne
description: 
external help file: ClusterAwareUpdating.dll-Help.xml
manager: jasgro
Module Name: ClusterAwareUpdating
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/clusterawareupdating/get-caureport?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CauReport
---

# Get-CauReport

## SYNOPSIS
Retrieves the Updating Run reports for all known Updating Runs, or all Updating Runs that match the specified dates or other specified parameters.

## SYNTAX

### AllParamsSet (Default)
```
Get-CauReport [[-ClusterName] <String>] [-Detailed] [-Credential <PSCredential>] [<CommonParameters>]
```

### RangeParamSet
```
Get-CauReport [[-ClusterName] <String>] [[-StartDate] <DateTime>] [[-EndDate] <DateTime>] [-Detailed]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### LastParamSet
```
Get-CauReport [[-ClusterName] <String>] [-Last] [-Detailed] [-Credential <PSCredential>] [<CommonParameters>]
```

### SpecificReportParamSet
```
Get-CauReport [[-ClusterName] <String>] [-Report <CauReportSummary>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-CauReport** cmdlet retrieves the Updating Run reports for all known Updating Runs, or all Updating Runs that match the specified dates or other specified parameters.
This cmdlet can return a list of all Updating Run reports between the specified **StartDate** and **EndDate** parameters, or if the **Last** parameter is specified instead of dates, then the cmdlet returns the most recent Updating Run report.
By default, the report contains summaries only, but more detail can be obtained with the **Detailed** parameter or by using the **Report** parameter and specifying a Cluster-Aware Updating (CAU) report summary object for which to return the detailed results.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-CauReport -ClusterName Contoso-FC1 -StartDate 01/01/2012 -Detailed
```

This example returns a detailed list of the Updating Runs performed on the cluster called Contoso-FC1 on 01/01/2012 or later.

### EXAMPLE 2
```
PS C:\> Get-CauReport -ClusterName Contoso-FC1 -StartDate 01/01/2012 -EndDate 04/01/2012 -Detailed
```

This example returns a detailed list of the Updating Runs performed on the cluster called Contoso-FC1 starting with Updating Runs on 01/01/2012 and ending with Updating Runs on 04/01/2012.

### EXAMPLE 3
```
PS C:\> $CauReportSummary=Get-CauReport Contoso-FC1 -Last
PS C:\>Get-CauReport Contoso-FC1 -Report $CauReportSummary
```

This example uses a CAU report summary object called $CauReportSummary to return a detailed report of the last Updating Run performed on the cluster called Contoso-FC1.

## PARAMETERS

### -ClusterName
Specifies the name of the cluster for which to retrieve reports.
This parameter is only required when this cmdlet is not run on a failover cluster node, or this cmdlet is used to reference a failover cluster different from where the cmdlet is run.

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
Specifies that the full results for one or more runs will be returned, instead of just summary information.

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
Retrieves only the reports for Runs before this time.

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
Retrieves only the most recent Run report.

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
Retrieves detailed results for the Run represented by the specified report summary.

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
Retrieves only the reports from Runs on or after this time.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ClusterAwareUpdating.CauReportSummary

## OUTPUTS

### Microsoft.ClusterAwareUpdating.CauReport

### Microsoft.ClusterAwareUpdating.CauReportSummary

## NOTES

## RELATED LINKS

[Export-CauReport](./Export-CauReport.md)

