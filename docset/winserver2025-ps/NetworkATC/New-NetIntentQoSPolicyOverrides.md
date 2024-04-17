---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/networkatc/new-netintentqospolicyoverrides?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetIntentQoSPolicyOverrides
---

# New-NetIntentQoSPolicyOverrides

## SYNOPSIS

Creates a new instance of **QoSPolicyOverrides** which can be used to supply granular values to
`Set-NetIntent`

## SYNTAX

```
New-NetIntentQoSPolicyOverrides [-PriorityValue8021Action_SMB <Byte>]
 [-PriorityValue8021Action_Cluster <Byte>] [-BandwidthPercentage_SMB <Byte>]
 [-BandwidthPercentage_Cluster <Byte>] [-NetDirectPortMatchCondition <Int32>] [<CommonParameters>]
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

### -BandwidthPercentage_Cluster

{{ Fill BandwidthPercentage_Cluster Description }}

```yaml
Type: System.Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -BandwidthPercentage_SMB

{{ Fill BandwidthPercentage_SMB Description }}

```yaml
Type: System.Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetDirectPortMatchCondition

{{ Fill NetDirectPortMatchCondition Description }}

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -PriorityValue8021Action_Cluster

{{ Fill PriorityValue8021Action_Cluster Description }}

```yaml
Type: System.Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -PriorityValue8021Action_SMB

{{ Fill PriorityValue8021Action_SMB Description }}

```yaml
Type: System.Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
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
