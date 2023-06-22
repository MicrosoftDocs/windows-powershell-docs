---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vhd?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-VHD

## SYNOPSIS
Set properties associated with a virtual hard disk.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VHD [-Path] <String> [-ParentPath] <String> [-ComputerName <String[]>] [-IgnoreIdMismatch]
 [-LeafPath <String>] [-Passthru] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-VHD [-Path] <String> [-ComputerName <String[]>] [-Passthru] -PhysicalSectorSizeBytes <UInt32> [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Set-VHD** cmdlet sets the ParentPath or PhysicalSectorSizeBytes properties of a virtual hard disk.
The two properties must be set in separate operations.

## EXAMPLES

### Example 1
```
PS C:\>Set-VHD -Path Child1.vhd -ParentPath ParentCopy.vhd -LeafPath Child2.vhd
```

This example sets the parent of the virtual hard disk associated with ParentCopy.vhd as the parent of the chained virtual hard disk associated with Child1.vhd, where the leaf of the virtual disk chain is the virtual hard disk associated with Child2.vhd.
The operation is performed in online mode.

### Example 2
```
PS C:\>Set-VHD -Path Child1.vhd -ParentPath ParentCopy.vhd
```

This example sets the parent of the virtual hard disk associated with ParentCopy.vhd as the parent of the chained virtual hard disk associated with Child1.vhd.
This operation cannot be performed when the virtual disk chain is attached.

### Example 3
```
PS C:\>Set-VHD -Path Child1.vhd -parentpath parentcopywithnewid.vhd -IgnoreIdMismatch
```

This example sets the parent of Child1.vhd to point to parentcopywithnewid.vhd, even though parentcopywithnewid.vhd has a different ID than the original parent of child1.vhd.
The operation is performed in offline mode.
This mode should be used with extreme caution, and only when it is certain that the block contents of the new and old parents are exactly the same.
Otherwise data loss can occur.

### Example 4
```
PS C:\> Set-VHD -Path c:\test.vhdx -PhysicalSectorSizeBytes 512
```

This example sets the physical sector size of a VHDX to 512 bytes.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the parent of a virtual hard disk in a differencing hard disk chain is to be set.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreIdMismatch
Specifies that the check for identifier mismatch between the parent and child virtual hard disk is to be skipped.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: FALSE
Accept pipeline input: False
Accept wildcard characters: False
```

### -LeafPath
Specifies the path to the virtual hard disk file of the virtual hard disk representing the leaf node of the virtual hard disk chain.
Required when performing the operation in online mode.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ParentPath
Specifies the path to the parent disk of a differencing virtual hard disk.
Can be performed regardless of whether the disk is online or offline.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the virtual hard disk whose parent is to be set.

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
Specifies the path to the virtual hard disk file of the virtual hard disk drive whose parent in the virtual hard disk chain is to be set.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: True
```

### -PhysicalSectorSizeBytes
Specifies the physical sector size, in bytes.
Valid values are 512 and 4096.
This parameter is supported only on a VHDX-format disk that is not attached when the operation is initiated.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
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

## OUTPUTS

## NOTES

## RELATED LINKS



