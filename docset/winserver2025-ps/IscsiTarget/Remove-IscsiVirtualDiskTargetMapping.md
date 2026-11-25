---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iscsitarget/remove-iscsivirtualdisktargetmapping?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-IscsiVirtualDiskTargetMapping
---

# Remove-IscsiVirtualDiskTargetMapping

## SYNOPSIS
Removes the assignment between the specified iSCSI virtual disk and the specified iSCSI target.

## SYNTAX

```
Remove-IscsiVirtualDiskTargetMapping [-TargetName] <String> [-Path] <String> [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-IscsiVirtualDiskTargetMapping** cmdlet removes the assignment between a virtual disk and an iSCSI target.
The virtual disk is no longer accessible by an iSCSI initiator after the assignment is removed.

## EXAMPLES

### Example 1: Disassociates a virtual disk from a target
```
PS C:\> Remove-IscsiVirtualDiskTargetMapping -TargetName "TargetOne" -Path "E:\temp\vhd1.vhdx"
```

This example un-assigns, or disassociates, the virtual disk at E:\temp\vhd1.vhdx from the target named TargetOne.
Use Add-IscsiVirtualDiskTargetMapping to assign the virtual disk to an iSCSI target before it can be used by an iSCSI initiator.

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

[Add-IscsiVirtualDiskTargetMapping](./Add-IscsiVirtualDiskTargetMapping.md)

