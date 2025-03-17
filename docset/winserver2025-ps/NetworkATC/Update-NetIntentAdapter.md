---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/update-netintentadapter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-NetIntentAdapter
---

# Update-NetIntentAdapter

## SYNOPSIS
Updates the network intent configuration for specified network adapters.

## SYNTAX

```
Update-NetIntentAdapter [-AdapterName] <String[]> [[-ClusterName] <String>]
 [[-ComputerName] <String>] [-Name] <String> [-Wait] [<CommonParameters>]
```

## DESCRIPTION

The `Update-NetIntentAdapter` cmdlet updates the configuration of network
adapters to align with the specified network intent. It can be used on
individual computers or across clusters.

## EXAMPLES

### Example 1

```powershell
Update-NetIntentAdapter -AdapterName "Ethernet1" -Name "MyIntent" -ComputerName "Server01"
```

This example updates the configuration of the adapter named `Ethernet1` on the
computer `Server01` to match the network intent named `MyIntent`.

## PARAMETERS

### -AdapterName

Specifies the network adapter(s) to be updated. This parameter accepts an array of adapter names.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterName

Specifies the name of the cluster on which to update the network intent
configuration across all nodes.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Specifies the name of the computer on which to update the network intent
configuration for the specified adapter(s).

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Specifies the name of the network intent to be applied to the adapter(s).

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

Indicates that the cmdlet waits for the operation to complete before returning
control to the command line.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction,
-ErrorVariable, -InformationAction, -InformationVariable, -OutVariable,
-OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

- [Update-NetIntentType](Update-NetIntentType.md)

- [Update-NetworkATC](Update-NetworkATC.md)
