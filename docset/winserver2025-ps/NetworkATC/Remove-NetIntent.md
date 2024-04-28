---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/networkatc/remove-netintent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-NetIntent
---

# Remove-NetIntent

## SYNOPSIS

Removes the requested net intent.

## SYNTAX

### ComputerName (Default)

```
Remove-NetIntent [-Name] <String> [[-ComputerName] <String>] [-SkipServiceStop <Boolean>]
 [<CommonParameters>]
```

### Cluster

```
Remove-NetIntent [-Name] <String> [-ClusterName] <String> [-SkipServiceStop <Boolean>]
 [<CommonParameters>]
```

### Global

```
Remove-NetIntent [-GlobalOverrides] [-SkipServiceStop <Boolean>] [<CommonParameters>]
```

## DESCRIPTION

This command removes the given Intent.

If the a **ClusterName** is specified, then the removal would impact all the nodes on the given
cluster. Otherwise, only net intents for a given node will be removed.

`Remove-NetIntent` doesn't remove the provisioning on the target hosts. The device administrator
should remove any old intent configuration from the node manually.

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
Position: 2
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
Position: 2
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
Position: 2
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
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipServiceStop

{{ Fill SkipServiceStop Description }}

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
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
