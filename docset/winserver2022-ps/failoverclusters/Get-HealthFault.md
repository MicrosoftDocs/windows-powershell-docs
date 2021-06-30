---
external help file: Microsoft.FailoverClusters.Health.PowerShell-help.xml
Module Name: FailoverClusters
online version:
schema: 2.0.0
---

# Get-HealthFault

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByCluster (Default)
```
Get-HealthFault [[-Cluster] <Cluster>] [-CimSession <CimSession>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByApi
```
Get-HealthFault [-ReportingType] <Object> [-ReportingKey] <Object> [-CimSession <CimSession>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -CimSession
{{ Fill CimSession Description }}

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cluster
{{ Fill Cluster Description }}

```yaml
Type: Cluster
Parameter Sets: ByCluster
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ReportingKey
{{ Fill ReportingKey Description }}

```yaml
Type: Object
Parameter Sets: ByApi
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportingType
{{ Fill ReportingType Description }}

```yaml
Type: Object
Parameter Sets: ByApi
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
