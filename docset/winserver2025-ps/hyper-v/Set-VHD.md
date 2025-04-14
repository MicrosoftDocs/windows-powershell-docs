---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vhd?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VHD
---

# Set-VHD

## SYNOPSIS
Sets properties associated with a virtual hard disk.

## SYNTAX

### Parent (Default)
```
Set-VHD [-Path] <String> [-ParentPath] <String> [-LeafPath <String>] [-IgnoreIdMismatch] [-Passthru]
 [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### PhysicalSectorSize
```
Set-VHD [-Path] <String> -PhysicalSectorSizeBytes <UInt32> [-Passthru] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DiskIdentifier
```
Set-VHD [-Path] <String> [-ResetDiskIdentifier] [-Force] [-Passthru] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VHD** cmdlet sets the ParentPath or PhysicalSectorSizeBytes properties of a virtual hard disk.
The two properties must be set in separate operations.

## EXAMPLES

### Example 1
```
PS C:\> Set-VHD -Path Child1.vhd -ParentPath ParentCopy.vhd -LeafPath Child2.vhd
```

This example sets the parent of the virtual hard disk associated with ParentCopy.vhd as the parent of the chained virtual hard disk associated with Child1.vhd, where the leaf of the virtual disk chain is the virtual hard disk associated with Child2.vhd.
The operation is performed in online mode.

### Example 2
```
PS C:\> Set-VHD -Path Child1.vhd -ParentPath ParentCopy.vhd
```

This example sets the parent of the virtual hard disk associated with ParentCopy.vhd as the parent of the chained virtual hard disk associated with Child1.vhd.
This operation cannot be performed when the virtual disk chain is attached.

### Example 3
```
PS C:\> Set-VHD -Path Child1.vhd -parentpath parentcopywithnewid.vhd -IgnoreIdMismatch
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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the parent of a virtual hard disk in a differencing hard disk chain is to be set.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

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

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: DiskIdentifier
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreIdMismatch
Specifies that the check for identifier mismatch between the parent and child virtual hard disk is to be skipped.

```yaml
Type: SwitchParameter
Parameter Sets: Parent
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LeafPath
Specifies the path to the virtual hard disk file of the virtual hard disk representing the leaf node of the virtual hard disk chain.
Required when performing the operation in online mode.

```yaml
Type: String
Parameter Sets: Parent
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentPath
Specifies the path to the parent disk of a differencing virtual hard disk.
Can be performed regardless of whether the disk is online or offline.

```yaml
Type: String
Parameter Sets: Parent
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
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
Aliases: FullName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PhysicalSectorSizeBytes
Specifies the physical sector size, in bytes.
Valid values are 512 and 4096.
This parameter is supported only on a VHDX-format disk that is not attached when the operation is initiated.

```yaml
Type: UInt32
Parameter Sets: PhysicalSectorSize
Aliases:
Accepted values: 512, 4096

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResetDiskIdentifier
Indicates that the cmdlet modifies the disk identifier of the virtual disk associated with the virtual hard disk file.
The disk identifier is the SCSI Vital Product Data (VPD) Page 0x83h identifier associated with a disk.
Use this parameter only for a VHDX-format disk.

```yaml
Type: SwitchParameter
Parameter Sets: DiskIdentifier
Aliases:

Required: True
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

### Microsoft.Vhd.PowerShell.VirtualHardDisk

## NOTES

## RELATED LINKS

