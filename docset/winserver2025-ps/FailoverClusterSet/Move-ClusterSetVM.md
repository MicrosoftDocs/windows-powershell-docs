---
external help file: ClusterSetVM.cdxml-help.xml
Module Name: FailoverClusterSet
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/failoverclusterset/move-clustersetvm?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Move-ClusterSetVM
---

# Move-ClusterSetVM

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByName (Default)
```
Move-ClusterSetVM -VMName <String[]> [-Node] <String> [-MoveType <MSCLUSTER_ClusterSetVM_MoveType>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### ByVmId
```
Move-ClusterSetVM [-VMId] <String[]> [-Node] <String> [-MoveType <MSCLUSTER_ClusterSetVM_MoveType>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### ById
```
Move-ClusterSetVM -Id <UInt64[]> [-Node] <String> [-MoveType <MSCLUSTER_ClusterSetVM_MoveType>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)
```
Move-ClusterSetVM -InputObject <CimInstance[]> [-Node] <String> [-MoveType <MSCLUSTER_ClusterSetVM_MoveType>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
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

### -Id
{{ Fill Id Description }}

```yaml
Type: System.UInt64[]
Parameter Sets: ById
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
{{ Fill InputObject Description }}

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MoveType
{{ Fill MoveType Description }}

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.MSCLUSTER.MSFT_ClusterSetVM.MSCLUSTER_ClusterSetVM_MoveType
Parameter Sets: (All)
Aliases: MigrationType
Accepted values: Turnoff, Quick, Shutdown, ShutdownForce, Live

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Node
{{ Fill Node Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
{{ Fill PassThru Description }}

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

### -VMId
{{ Fill VMId Description }}

```yaml
Type: System.String[]
Parameter Sets: ByVmId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName
{{ Fill VMName Description }}

```yaml
Type: System.String[]
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### System.UInt64[]

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#root/microsoft/windows/cluster/scaleout/MSFT_ClusterSetVM

## NOTES

## RELATED LINKS
