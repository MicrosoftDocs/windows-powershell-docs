---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/merge-vhd?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Merge-VHD
---

# Merge-VHD

## SYNOPSIS
Merges virtual hard disks.

## SYNTAX

```
Merge-VHD [-Path] <String> [[-DestinationPath] <String>] [-Force] [-AsJob] [-Passthru]
 [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Merge-VHD** cmdlet merges virtual hard disks in a differencing virtual hard disk chain.
The merge is from a specified source child disk to a specified destination child disk.

Merge is an offline operation; the virtual hard disk chain must not be attached when merge is initiated.

## EXAMPLES

### Example 1
```
PS C:\> Merge-VHD -Path c:\test\VDisk4.avhdx -DestinationPath c:\test\VDisk2.avhdx
```

This example merges the virtual hard disk from VDisk4 to VDisk2. It merges all data from VDisk4 and
VDisk3, up to VDisk2. In this virtual hard disk chain VDisk4 is a child of VDisk3, which is a child
of VDisk2, which is a child of VDisk1. Finally, VDisk1 is a child of the Parent virtual hard disk.

In this example, all referenced virtual hard disks reside within `C:\test`. The `VDisk4.avhdx` and
`VDisk3.avhdx` are not deleted, however, they are no longer valid virtual hard disk files after the
operation completes.

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
Specifies one or more Hyper-V hosts on which virtual hard disks are to be merged.
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

### -DestinationPath
Specifies the path to the child in the virtual hard disk chain that is the destination for the merge command.

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

### -Force
Runs the cmdlet without prompting for confirmation.

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

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the merged virtual hard disk.

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
Specifies the path to the child in the virtual hard disk chain that is the source for the merge command.
If a filename or relative path is specified, the virtual hard disk path will be calculated relative to the current working directory.

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

### VHDObject

## OUTPUTS

### Microsoft.Vhd.PowerShell.VirtualHardDisk

## NOTES

## RELATED LINKS

