---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Get-VMSwitchExternalPortId.psm1-help.xml
Module Name: HNVDiagnostics
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hnvdiagnostics/get-vmswitchexternalportid?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMSwitchExternalPortId
---

# Get-VMSwitchExternalPortId

## SYNOPSIS
Gets the VFP/VSwitch port ID for the external port for a virtual switch.

## SYNTAX

```
Get-VMSwitchExternalPortId [-SwitchName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMSwitchExternalPortId** cmdlet gets the VFP/VSwitch port ID for the external port of a virtual switch.

## EXAMPLES

### Example 1: Get the port ID of a virtual switch
```
PS C:\> Get-VMSwitchExternalPortId -SwitchName "ExternalPrivate"
```

This command gets the VFP/VSwitch port ID for the switch named ExternalPrivate.

## PARAMETERS

### -SwitchName
Specifies the name of a virtual switch.
This cmdlet get the port ID for the switch that you specify.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

