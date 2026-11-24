---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iscsitarget/add-iscsivirtualdisktargetmapping?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-IscsiVirtualDiskTargetMapping
---

# Add-IscsiVirtualDiskTargetMapping

## SYNOPSIS
Assigns a virtual disk to an iSCSI target.

## SYNTAX

```
Add-IscsiVirtualDiskTargetMapping [-TargetName] <String> [-Path] <String> [-Lun <Int32>]
 [-ComputerName <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-IscsiVirtualDiskTargetMapping** cmdlet assigns a virtual disk to an iSCSI target.
Once a virtual disk has been assigned to a target, and after the iSCSI initiator connects to that target, the iSCSI initiator can access the virtual disk.
All of the virtual disks assigned to the same iSCSI target can be accessed by the connected iSCSI initiator.

## EXAMPLES

### Example 1: Associate a VHD with a target
```
PS C:\> Add-IscsiVirtualDiskTargetMapping -TargetName "TargetOne" -DevicePath "E:\Temp\vhd1.vhdx"
```

This example associates the VHD with the path E:\Temp\vhd1.vhdx to the target named TargetOne.

### Example 2: Associate a VHD with a target and set the LUN
```
PS C:\> Add-IscsiVirtualDiskTargetMapping -TargetName "TargetOne" -DevicePath "E:\Temp\vhd1.vhdx" -Lun 0
```

This example associates the VHD with the path E:\Temp\vhd1.vhdx to the target named TargetOne, and sets the LUN to 0.
It is important that the LUN number for a given target is unique.

### Example 3: Associate a ramdisk with a target
```
PS C:\> Add-IscsiVirtualDiskTargetMapping -TargetName "TestTarget" -Path "ramdisk:test.vhdx"
```

This example assigns the ramdisk called test to the target object named TestTarget.
If the initiator connects to the TestTarget, it can access the RAMdisk.

## PARAMETERS

### -ComputerName
Specifies the computer name, or IP address, of the remote computer, if this cmdlet is run on a remote computer.

Specifies the cluster resource group network name, or cluster node name, if this cmdlet is run on a cluster configuration.

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

### -Lun
Specifies the logical unit number (LUN) associated with the virtual disk.
By default, the lowest available LUN number is assigned.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path of the virtual hard disk (VHD) file that is associated with the iSCSI virtual disk.
Filter the iSCSI Virtual Disk object by using this parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DevicePath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetName
Specifies the name of the iSCSI target.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Remove-IscsiVirtualDiskTargetMapping](./Remove-IscsiVirtualDiskTargetMapping.md)

