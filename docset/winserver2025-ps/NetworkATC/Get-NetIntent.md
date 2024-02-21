---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/networkatc/get-netintent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetIntent
---

# Get-NetIntent

## SYNOPSIS
Gets the current set of intents configured on the node / cluster

## SYNTAX

### ComputerName (Default)

```
Get-NetIntent [[-ComputerName] <String>] [-Name <String>] [-GlobalOverrides] [<CommonParameters>]
```

### Cluster

```
Get-NetIntent [-ClusterName] <String> [-Name <String>] [-GlobalOverrides] [<CommonParameters>]
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

### -ClusterName

{{ Fill ClusterName Description }}

```yaml
Type: System.String
Parameter Sets: Cluster
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

{{ Fill ComputerName Description }}

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GlobalOverrides

{{ Fill GlobalOverrides Description }}

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

### -Name

{{ Fill Name Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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
