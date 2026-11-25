---
external help file: ClusterSet.cdxml-help.xml
Module Name: FailoverClusterSet
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/failoverclusterset/get-clustersetoptimalnodeforvm?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterSetOptimalNodeForVm
---

# Get-ClusterSetOptimalNodeForVm

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### DefaultSet (Default)
```
Get-ClusterSetOptimalNodeForVm [<CommonParameters>]
```

### InputObject (cdxml)
```
Get-ClusterSetOptimalNodeForVm [-InputObject <CimInstance[]>] -VmMemory <UInt32> [-VmVirtualCoreCount <UInt32>]
 [-VmCpuReservation <UInt32>] [-VmFlags <UInt32>] [-PlacementCondition <String>]
 [-AvailabilitySetName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
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
Parameter Sets: InputObject (cdxml)
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
Parameter Sets: InputObject (cdxml)
Aliases: AvailabilitySet

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
{{ Fill CimSession Description }}

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: InputObject (cdxml)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
{{ Fill InputObject Description }}

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PlacementCondition
{{ Fill PlacementCondition Description }}

```yaml
Type: System.String
Parameter Sets: InputObject (cdxml)
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
Parameter Sets: InputObject (cdxml)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VmCpuReservation
{{ Fill VmCpuReservation Description }}

```yaml
Type: System.UInt32
Parameter Sets: InputObject (cdxml)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VmFlags
{{ Fill VmFlags Description }}

```yaml
Type: System.UInt32
Parameter Sets: InputObject (cdxml)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VmMemory
{{ Fill VmMemory Description }}

```yaml
Type: System.UInt32
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VmVirtualCoreCount
{{ Fill VmVirtualCoreCount Description }}

```yaml
Type: System.UInt32
Parameter Sets: InputObject (cdxml)
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

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#root/microsoft/windows/scaleout/MSFT_ClusterSetNode

## NOTES

## RELATED LINKS
