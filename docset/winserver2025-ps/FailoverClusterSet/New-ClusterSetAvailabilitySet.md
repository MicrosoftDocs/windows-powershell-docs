---
external help file: ClusterSetAvailabilitySet.cdxml-help.xml
Module Name: FailoverClusterSet
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/failoverclusterset/new-clustersetavailabilityset?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-ClusterSetAvailabilitySet
---

# New-ClusterSetAvailabilitySet

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

```
New-ClusterSetAvailabilitySet [-AvailabilitySetName] <String> -FDType <MSCluster_ClusterSet_FaultDomainType>
 [-ParticipantName <String[]>] [-SoftEnforcement <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
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

### -AsJob
{{ Fill AsJob Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AvailabilitySetName
{{ Fill AvailabilitySetName Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
{{ Fill CimSession Description }}

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FDType
{{ Fill FDType Description }}

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.MSCLUSTER.MSFT_ClusterSetAvailabilitySet.MSCluster_ClusterSet_FaultDomainType
Parameter Sets: (All)
Aliases: FaultDomainType
Accepted values: Logical, Node

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParticipantName
{{ Fill ParticipantName Description }}

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SoftEnforcement
{{ Fill SoftEnforcement Description }}

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
{{ Fill ThrottleLimit Description }}

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#root/microsoft/windows/cluster/scaleout/MSFT_ClusterSetAvailabilitySet

## NOTES

## RELATED LINKS
