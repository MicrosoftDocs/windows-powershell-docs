---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Optimize-VHD

## SYNOPSIS
Optimizes the allocation of space used by virtual hard disk files, except for fixed virtual hard disks.

## SYNTAX

```
Optimize-VHD [-Path] <String[]> [-AsJob] [-ComputerName <String[]>] [-Mode <VhdCompactMode>] [-Passthru]
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Optimize-VHD** cmdlet optimizes the allocation of space in or more virtual hard disk files, except for fixed virtual hard disks.
The **Compact** operation is used to optimize the files.
This operation reclaims unused blocks as well as rearranges the blocks to be more efficiently packed, which reduces the size of a virtual hard disk file.

To use Optimize-VHD, the virtual hard disk must not be attached or must be attached in read-only mode.

The compact operation can succeed without reducing the file size, if no optimization is possible.

## EXAMPLES

### Example 1
```
PS C:\>Optimize-VHD -Path c:\test\dynamic.vhdx -Mode Full
```

Runs the compact operation in Full mode.
(If the VHDX-format file is not attached as read-only prior to the operation, it will default to Prezeroed mode.)

### Example 2
```
PS C:\> Optimize-VHD -Path c:\test\dynamic.vhdx -Mode Retrim
```

Runs the compact operation in Retrim mode.
(If the VHDX-format disk is not mounted as read-only prior to the operation, running the cmdlet returns an error.)

### Example 3
```
PS C:\>Optimize-VHD -Path c:\test\dynamic.vhdx -Mode Quick
```

Runs the compact operation in Quick mode.
(If the VHDX-format file is not attached as read-only prior to the operation, it defaults to Pretrimmed mode.)

## PARAMETERS

### -AsJob
Specifies that the cmdlet is to be run as a background job.

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
Specifies one or more Hyper-V hosts on which a virtual machine is to be optimized.
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

### -Mode
Specifies the mode in which the virtual hard disk is to be optimized.
For a **VHD** disk, the default mode is **Full**.
For a **VHDX** disk, the default mode is **Quick**.
Valid modes are as follows:

--**Full** scans for zero blocks and reclaims unused blocks. (Allowable only if the virtual hard disk is mounted read-only.)
--**Pretrimmed** performs as **Quick** mode, but does not require the virtual hard disk to be mounted read-only. The detection of unused space is less effective than **Quick** mode (in which the virtual hard disk had been mounted read-only) because the scan cannot query information about free space in the NTFS file system within the virtual hard disk. Useful when the VHDX-format file has been used by operating system instances that are at least Windows 8 or Windows Server 2012, or when this cmdlet has already been run on a .vhdx file in **Retrim** mode.
--**Prezeroed** performs as **Quick** mode, but does not require the virtual hard disk to be mounted read-only. The unused space detection will be less effective than if the virtual hard disk had been mounted read-only as the scan will be unable to query information about free space in the NTFS file system within the virtual hard disk. Useful if a tool was run previously to zero all the free space on the virtual disk as this mode of compaction can then reclaim that space for subsequent block allocations. This form of compaction can also be useful in handling virtual hard disk containing file systems other than NTFS.
--**Quick** reclaims unused blocks, but does not scan for zero blocks. (Allowable only if the virtual hard disk is mounted read-only.)
--**Retrim** sends down retrims without scanning for zero blocks or reclaiming unused blocks. (Allowable only if the virtual hard disk is mounted read-only.)

```yaml
Type: VhdCompactMode
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the virtual hard disk to be optimized.

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
Specifies one or more paths to the dynamic or differencing virtual hard disk files to be optimized.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: FullName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
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

[00000000-0000-0000-0000-000000000000](00000000-0000-0000-0000-000000000000)

