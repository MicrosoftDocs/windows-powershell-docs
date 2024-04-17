---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/networkatc/set-netintentretrystate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetIntentRetryState
---

# Set-NetIntentRetryState

## SYNOPSIS
Changes the provisioning state of the goal state for an intent on a given host.

## SYNTAX

### ComputerName (Default)

```
Set-NetIntentRetryState [-ComputerName <String>] -Name <String> [-Wait] [<CommonParameters>]
```

### Global

```
Set-NetIntentRetryState [-ClusterName <String>] [-ComputerName <String>] [-NodeName <String>] [-Wait]
 [-GlobalOverrides] [<CommonParameters>]
```

### Cluster

```
Set-NetIntentRetryState [-ClusterName <String>] -Name <String> -NodeName <String> [-Wait] [<CommonParameters>]
```

## DESCRIPTION

Use this to reset failed provisioning. The state of the request is reset to `RetryRequired`.

## EXAMPLES

### Example 1

```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -ClusterName

{{ Fill ClusterName Description }}

```yaml
Type: System.String
Parameter Sets: Global, Cluster
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

{{ Fill ComputerName Description }}

```yaml
Type: System.String
Parameter Sets: ComputerName, Global
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GlobalOverrides

{{ Fill GlobalOverrides Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Global
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

{{ Fill Name Description }}

```yaml
Type: System.String
Parameter Sets: ComputerName, Cluster
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeName

{{ Fill NodeName Description }}

```yaml
Type: System.String
Parameter Sets: Global
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: Cluster
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

{{ Fill Wait Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

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
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
