---
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
online version: 
schema: 2.0.0
title: Add-IscsiVirtualDiskTargetMapping
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 373AE22C-2936-4D5C-A99E-12E2E31A7E03
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
Once a virtual disk has been assigned to a target, and after the iSCSi initiator connects to that target, the iSCSI initiator can access the virtual disk.
All of the virtual disks assigned to the same iSCSI target will be accessible by the connected iSCSI initiator.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Add-IscsiVirtualDiskTargetMapping -TargetName "TargetOne" -DevicePath "E:\Temp\vhd1.vhdx"
```

This example associates the VHD with the path E:\Temp\vhd1.vhdx to the target named TargetOne.

### EXAMPLE 2
```
PS C:\> Add-IscsiVirtualDiskTargetMapping -TargetName "TargetOne" -DevicePath "E:\Temp\vhd1.vhdx" -Lun 0
```

This example associates the VHD with the path E:\Temp\vhd1.vhdx to the target named TargetOne, and sets the LUN to 0.
It is important that theLUN number for a given target is unique.

### EXAMPLE 3
```
PS C:\>Add-IscsiVirtualDiskTargetMapping -TargetName TestTarget -Path ramdisk:test.vhdx
```

This example assigns the ramdisk called test to the target object named TestTarget.
When the initiator connects to the TestTarget, it will be able to access the RAMdisk.

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
By default, the lowest available LUN number will be assigned.

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
                         
Filter the iSCSI Virtual Disk object using this parameter.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Remove-IscsiVirtualDiskTargetMapping](./Remove-IscsiVirtualDiskTargetMapping.md)

