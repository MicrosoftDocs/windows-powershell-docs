---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/update-netintenttype?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-NetIntentType
---

# Update-NetIntentType

## SYNOPSIS
Updates the configuration types of network intents for specified computers or clusters.

## SYNTAX

### ComputerName (Default)

```
Update-NetIntentType [-Name] <String> [[-ComputerName] <String>] [-Wait] [-Compute] [-Management]
 [-Storage] [-Stretch] [<CommonParameters>]
```

### Cluster

```
Update-NetIntentType [-Name] <String> [-ClusterName] <String> [-Wait] [-Compute] [-Management]
 [-Storage] [-Stretch] [<CommonParameters>]
```

## DESCRIPTION

The `Update-NetIntentType` cmdlet updates the configuration types (such as Compute, Management,
Storage, and Stretch) for a specified network intent across individual computers or an entire
cluster.

## EXAMPLES

### Example 1

```powershell
Update-NetIntentType -Name "MyIntent" -ComputerName "Server01" -Compute -Wait
```

This example updates the network intent named `MyIntent` on the computer `Server01` to include the
**Compute** configuration type and waits for the operation to complete before returning control.

## PARAMETERS

### -ClusterName

Specifies the name of the cluster on which to update the network intent types across all nodes.

```yaml
Type: String
Parameter Sets: Cluster
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Compute

Indicates that the Compute configuration type should be included in the update.

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

### -ComputerName

Specifies the name of the computer on which to update the network intent types.

```yaml
Type: String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Management

Indicates that the Management configuration type should be included in the update.

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

### -Name

Specifies the name of the network intent to be updated.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Storage

Indicates that the Storage configuration type should be included in the update.

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

### -Stretch

Indicates that the Stretch configuration type should be included in the update.

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

### -Wait

Indicates that the cmdlet waits for the operation to complete before returning control to the
command line.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Update-NetIntentAdapter](Update-NetIntentAdapter.md)

[Update-NetworkATC](Update-NetworkATC.md)
