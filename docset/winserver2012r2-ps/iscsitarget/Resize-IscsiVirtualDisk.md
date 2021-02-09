---
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
online version: 
schema: 2.0.0
title: Resize-IscsiVirtualDisk
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 67564801-F38C-4E86-B4FA-900883CE4F9C
---

# Resize-IscsiVirtualDisk

## SYNOPSIS
Resizes an iSCSI virtual disk.

## SYNTAX

### Path (Default)
```
Resize-IscsiVirtualDisk [-Path] <String> [-Size] <UInt64> [-PassThru] [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### InputObject
```
Resize-IscsiVirtualDisk -InputObject <IscsiVirtualDisk> [-Size] <UInt64> [-PassThru] [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Resize-IscsiVirtualDisk** cmdlet resizes a virtual disk either by expanding or compacting an existing virtual disk.
Virtual disks that use the VHDX format can remain online while the cmdlet resizes them.
If the cmdlet resizes an online disk, when the virtual disk is mapped to an iSCSI Target, initiators can continue to access the virtual disk even while the cmdlet resizes it.
However, an initiator will not automatically see the resized virtual disk.
To get access to the capacity of the expanded virtual disk, the initiator must use the Resize-Partition cmdlet to modify the volume hosted on the virtual disk.

This cmdlet can compact a disk only when the logical unit number (LUN) on the initiator side created some partitions on the LUN, and the compacting process simply shrinks the unallocated part of the LUN.

## EXAMPLES

### Example 1: Resize a virtual disk
```
PS C:\> Resize-IscsiVirtualDisk -Path "E:\temp\test06.vhdx" -Size 20GB
```

This command resizes the virtual disk at the path E:\temp\test06.vhdx to 20GB.

## PARAMETERS

### -ComputerName
Specifies the computer name, or IP address, of the remote computer, if this cmdlet is run on a remote computer. 

Specifies the cluster resource group network name, or cluster node name, if this cmdlet is run on a cluster configuration.

If you do not specify a value for this parameter, the cmdlet uses the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential
Specifies the credentials when connecting to a remote computer.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Accepts an iSCSI Virtual Disk object from the input pipeline.

```yaml
Type: IscsiVirtualDisk
Parameter Sets: InputObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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
Specifies the path of the virtual hard disk (VHDX) file that is associated with the iSCSI virtual disk. 

Filter the iSCSI Virtual Disk object using this parameter.

```yaml
Type: String
Parameter Sets: Path
Aliases: DevicePath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Size
Specifies the size of the resized iSCSI virtual disk. 
Note: This parameter takes a number and a unit as input, such as 10GB, 20MB, or 1TB. 

If you do not specify this parameter, the cmdlet prompts you for a value.
You must enter the value in bytes, without specifying a unit.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Iscsi.Target.Commands.IscsiVirtualDisk

## OUTPUTS

### Microsoft.Iscsi.Target.Commands.IscsiVirtualDisk

## NOTES

## RELATED LINKS

[Resize-Partition](../storage/Resize-Partition.md)

[Checkpoint-IscsiVirtualDisk](./Checkpoint-IscsiVirtualDisk.md)

[Convert-IscsiVirtualDisk](./Convert-IscsiVirtualDisk.md)

[Get-IscsiVirtualDisk](./Get-IscsiVirtualDisk.md)

[Import-IscsiVirtualDisk](./Import-IscsiVirtualDisk.md)

[New-IscsiVirtualDisk](./New-IscsiVirtualDisk.md)

[Remove-IscsiVirtualDisk](./Remove-IscsiVirtualDisk.md)

[Restore-IscsiVirtualDisk](./Restore-IscsiVirtualDisk.md)

[Set-IscsiVirtualDisk](./Set-IscsiVirtualDisk.md)

