---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
ms.date: 09/27/2022
online version: https://learn.microsoft.com/powershell/module/clusterawareupdating/export-caureport?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-CauReport
---

# Export-CauReport

## SYNOPSIS
Exports one or more Updating Run reports into an HTML or CSV-formatted document.

## SYNTAX

```
Export-CauReport [-InputReport] <CauReport[]> [-Format] <OutputType> [-Path] <String> [-PassThru]
 [-Force] [-TimeZone <TimeZoneInfo>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Export-CauReport` cmdlet exports one or more Updating Run reports into an HTML or
CSV-formatted document. Each Run report summarizes both the node-level and cluster-level summary
status for the Updating Run.

Pipe one or more reports from the `Get-CauReport` cmdlet with the **Detailed** parameter, and
control the content in the report by specifying appropriate parameters for the `Get-CauReport`
cmdlet. For example, the **Last** parameter specifies the most recent Updating Run.

## EXAMPLES

### Example 1: Get a detailed version of the last CAU report for the specified cluster

```powershell
$CauReport = Get-CauReport -ClusterName "Contoso-FC1" -Last -Detailed
$CauReport | Export-CauReport -Format HTML -Path "C:\temp\contoso-fc1_last.html" -TimeZone ([system.timezoneinfo]::Utc)
```

This command gets a detailed version of the last CAU report for the cluster named Contoso-FC1, then
exports that report in HTML format to the path `C:\temp\contoso-fc1_last.html`. The timestamps in
the report are formatted in the Coordinated Universal Time (UTC) zone.

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

Forces the command to run without asking for user confirmation.

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

Specifies an array of CAU report objects, such as generated from a call to Get-CauReport with the
**Detailed** parameter.

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

Returns an object representing the item with which you are working.
By default, this cmdlet doesn't generate any output.

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

Specifies the formatting of the report timestamps to match the specified time zone.

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
The cmdlet isn't run.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ClusterAwareUpdating.CauReport

## OUTPUTS

### Microsoft.ClusterAwareUpdating.CauReport

## NOTES

## RELATED LINKS

[Get-CauReport](./Get-CauReport.md)

[Invoke-CauRun](./Invoke-CauRun.md)

