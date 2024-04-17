---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/repair-vm?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Repair-VM

## SYNOPSIS
Repairs one or more virtual machines.

## SYNTAX

```
Repair-VM [-CompatibilityReport] <VMCompatibilityReport> [-ComputerName <String[]>] [-Passthru]
 [-Path <String>] [-SnapshotFilePath <String>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Repair-VM** cmdlet repairs one or more virtual machines.

## EXAMPLES

### Example 1
```
PS C:\>Repair-VM -CompatibilityReport $VMCompatReport -Path C:\Test
```

Changes the configuration path for a virtual machine compatibility report.

### Example 2
```
PS C:\>Repair-VM -CompatibilityReport $VMCompatReport -SnapshotFilePath C:\Snapshots
```

Adds missing snapshots to a virtual machine compatibility report.

## PARAMETERS

### -CompatibilityReport
Specifies a compatibility report which includes adjustments to be made during repair.

```yaml
Type: VMCompatibilityReport
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual machine or machines are to be repaired.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None
Default

### Microsoft.Virtualization.Powershell.CompatibilityReport
If **-PassThru** is specified.

## OUTPUTS

## NOTES

## RELATED LINKS



