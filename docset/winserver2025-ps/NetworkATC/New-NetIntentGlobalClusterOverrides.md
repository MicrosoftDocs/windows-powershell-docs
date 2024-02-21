---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/networkatc/new-netintentglobalclusteroverrides?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetIntentGlobalClusterOverrides
---

# New-NetIntentGlobalClusterOverrides

## SYNOPSIS
Creates a new instance of ClusterSettings which can be used to supply granular values to
`Add-NetIntent` and `Set-NetIntent`.

## SYNTAX

```
New-NetIntentGlobalClusterOverrides [[-EnableNetworkNaming] <Boolean>]
 [[-EnableLiveMigrationNetworkSelection] <Boolean>]
 [[-EnableVirtualMachineMigrationPerformanceSelection] <Boolean>]
 [[-VirtualMachineMigrationPerformanceOption] <String>] [[-MaximumVirtualMachineMigrations] <Byte>]
 [[-MaximumSMBMigrationBandwidthInGbps] <UInt32>] [<CommonParameters>]
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

### -EnableLiveMigrationNetworkSelection

{{ Fill EnableLiveMigrationNetworkSelection Description }}

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableNetworkNaming

{{ Fill EnableNetworkNaming Description }}

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableVirtualMachineMigrationPerformanceSelection

{{ Fill EnableVirtualMachineMigrationPerformanceSelection Description }}

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumSMBMigrationBandwidthInGbps

{{ Fill MaximumSMBMigrationBandwidthInGbps Description }}

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumVirtualMachineMigrations

{{ Fill MaximumVirtualMachineMigrations Description }}

```yaml
Type: System.Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualMachineMigrationPerformanceOption

{{ Fill VirtualMachineMigrationPerformanceOption Description }}

```yaml
Type: System.String
Parameter Sets: (All)
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
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
