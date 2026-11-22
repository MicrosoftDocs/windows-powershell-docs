---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/resize-vhd?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Resize-VHD
---

# Resize-VHD

## SYNOPSIS
Resizes a virtual hard disk.

## SYNTAX

### Size (Default)
```
Resize-VHD [-Path] <String[]> [-SizeBytes] <UInt64> [-AsJob] [-Passthru] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### MinimumSize
```
Resize-VHD [-Path] <String[]> [-ToMinimumSize] [-AsJob] [-Passthru] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Resize-VHD** cmdlet changes the maximum physical size of a virtual hard disk. It can expand both VHD and VHDX files but can shrink only VHDX files.
The shrink operation fails if it would shrink the virtual disk to less than its minimum size (available through the VHDX object's **MinimumSize** property).

If the virtual disk file connects to a virtual machine's IDE chain, you **cannot** resize the virtual disk while the virtual machine is online.
If the virtual disk file connects to a virtual machine's SCSI chain, you **can** resize the virtual disk while the virtual machine is online.

> [!NOTE]
> Resize-VHD does not remove empty blocks from a dynamically-expanding virtual hard disk file. Use Optimize-VHD instead.

## EXAMPLES

### Example 1
```
PS C:\> Resize-VHD -Path c:\BaseVHD.vhd -SizeBytes 1099511627776
```

Expands the VHD to 1 terabyte if the previous size was less than 1 terabyte. If it was larger, the cmdlet will report an error because it cannot shrink a VHD.

### Example 2
```
PS C:\> Resize-VHD -Path c:\BaseVHDX.vhdx -SizeBytes 20GB
```

Changes the VHDX's size to 20 gigabytes (21,474,836,480 bytes). If it was larger, the cmdlet will only succeed if it had a **MinimumSize** less than or equal to 20 gigabytes.

### Example 3
```
PS C:\> Resize-VHD -Path c:\BaseVHDX.vhdx -ToMinimumSize
```

Shrinks the VHDX to its minimum possible size as indicated in its **MinimumSize** property.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.

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
Specifies one or more Hyper-V hosts on which a virtual hard disk is to be resized.
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

### -Passthru
Specifies that an object representing the resized virtual hard disk is to be passed through to the pipeline.

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
Specifies the path to the virtual hard disk that is to be resized.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: FullName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SizeBytes
Specifies the size to which the virtual hard disk is to be resized.

```yaml
Type: UInt64
Parameter Sets: Size
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToMinimumSize
Specifies that the virtual hard disk is to be resized to its minimum possible size.

```yaml
Type: SwitchParameter
Parameter Sets: MinimumSize
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

