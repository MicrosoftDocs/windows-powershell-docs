---
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/clusterawareupdating/export-caureport?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-CauReport
---

# Export-CauReport

## SYNOPSIS
Exports one or more Updating Run reports into an HTML or CSV-formatted document.

## SYNTAX

```
Export-CauReport [-InputReport] <CauReport[]> [-Format] <OutputType> [-Path] <String> [-PassThru] [-Force]
 [-TimeZone <TimeZoneInfo>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Export-CauReport** cmdlet exports one or more Updating Run reports into an HTML or CSV-formatted document.
Each Run report summarizes both the node-level and cluster-level summary status for the Updating Run.

Pipe one or more reports from the Get-CauReport cmdlet with the **Detailed** parameter, and control the content in the report by specifying appropriate parameters for the Get-CauReport cmdlet.
For example, the **Last** parameter specifies the most recent Updating Run.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-CauReport -ClusterName Contoso-FC1 -Last -Detailed | Export-CauReport -Format HTML -Path C:\temp\contoso-fc1_last.html -TimeZone ([system.timezoneinfo]::Utc)
```

This example gets a detailed version of the last CAU report for the cluster named Contoso-FC1, then exports that report in HTML format to the path C:\temp\contoso-fc1_last.html.
The timestamps in the report are formatted in the Coordinated Universal Time (UTC) zone.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Runs the cmdlet without prompting for confirmation.
By default the cmdlet will ask for confirmation from the user before proceeding.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Format
Specifies the format of the output report.
The acceptable values for this parameter are: CSV or HTML.

```yaml
Type: OutputType
Parameter Sets: (All)
Aliases: 
Accepted values: Csv, Html

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputReport
Specifies one or more CAU report objects, such as generated from a call to Get-CauReport with the **Detailed** parameter.

```yaml
Type: CauReport[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Passes the CAU report object back through the pipeline for further processing.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the local or complete path of the file to save the exported report.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeZone
Allows formatting of the report timestamps to match the specified time zone.

```yaml
Type: TimeZoneInfo
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ClusterAwareUpdating.CauReport

## OUTPUTS

### Microsoft.ClusterAwareUpdating.CauReport

## NOTES

## RELATED LINKS

[Get-CauReport](./Get-CauReport.md)

[Invoke-CauRun](./Invoke-CauRun.md)

