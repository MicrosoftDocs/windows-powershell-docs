---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/repair-vm?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Repair-VM
---

# Repair-VM

## SYNOPSIS
Repairs one or more virtual machines.

## SYNTAX

```
Repair-VM [-CompatibilityReport] <VMCompatibilityReport> [-SnapshotFilePath <String>] [-Path <String>]
 [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Repair-VM** cmdlet corrects some issues that can impact the ability to import or move a virtual machine.
If Compare-VM determines that an import or move operation would fail for a particular VM, it returns a collection of incompatibilities that need to be fixed before the operation can succeed.
Most of these incompatibilities can be fixed by using Set-VM.
However, Set-VM does not modify either the path where the VM configuration is stored or the path where the snapshot files are stored.
Repair-VM handles these two particular issues in this one specific situation.

## EXAMPLES

### Example 1
```
PS C:\> Repair-VM -CompatibilityReport $VMCompatReport -Path C:\Test
```

This example changes the configuration path for a virtual machine compatibility report.

### Example 2
```
PS C:\> Repair-VM -CompatibilityReport $VMCompatReport -SnapshotFilePath C:\Snapshots
```

This example adds missing snapshots to a virtual machine compatibility report.

## PARAMETERS

### -CompatibilityReport
Specifies a compatibility report which includes adjustments to be made during repair.

```yaml
Type: VMCompatibilityReport
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the newly modified compatibility report.

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

### -Path
Specifies the path of the virtual machine to be repaired.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SnapshotFilePath
Specifies the path to be search for virtual machine snapshots.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CheckpointFileLocation, SnapshotFileLocation

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.HyperV.PowerShell.CompatibilityReport
If **-PassThru** is specified.

## NOTES

## RELATED LINKS

