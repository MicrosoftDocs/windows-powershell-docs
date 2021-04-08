---
author: Kateyanne
external help file: ClusterAware_Cmdlets.xml
manager: dansimp
Module Name: ClusterAwareUpdating
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/clusterawareupdating/get-caureport?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-CauReport

## SYNOPSIS
Retrieves the Updating Run reports for all known Updating Runs, or all Updating Runs that match the specified dates or other specified parameters.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-CauReport [[-ClusterName] <String>] [-Credential <PSCredential>] [-Detailed]
```

### UNNAMED_PARAMETER_SET_2
```
Get-CauReport [[-ClusterName] <String>] [-Credential <PSCredential>] [-Detailed] [-Last]
```

### UNNAMED_PARAMETER_SET_3
```
Get-CauReport [[-ClusterName] <String>] [[-StartDate] <DateTime>] [[-EndDate] <DateTime>]
 [-Credential <PSCredential>] [-Detailed]
```

### UNNAMED_PARAMETER_SET_4
```
Get-CauReport [[-ClusterName] <String>] [-Credential <PSCredential>] [-Report <CauReportSummary>]
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
Get-CauReport Contoso-FC1 -Report $CauReportSummary
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
Position: 1
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Last
Retrieves only the most recent Run report.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_4
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.ClusterAwareUpdating.CauReportSummary

## OUTPUTS

### Microsoft.ClusterAwareUpdating.CauReport

### Microsoft.ClusterAwareUpdating.CauReportSummary

## NOTES

## RELATED LINKS

[Export-CauReport](./Export-CauReport.md)

