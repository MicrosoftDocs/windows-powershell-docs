---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iscsitarget/restore-iscsivirtualdisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-IscsiVirtualDisk
---

# Restore-IscsiVirtualDisk

## SYNOPSIS
Restores a virtual disk from a snapshot.

## SYNTAX

### SnapshotId (Default)
```
Restore-IscsiVirtualDisk [-SnapshotId] <String> [-ComputerName <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### InputObject
```
Restore-IscsiVirtualDisk -InputObject <IscsiVirtualDiskSnapshot> [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Restore-IscsiVirtualDisk** cmdlet restores an iSCSI virtual disk using its snapshot.

## EXAMPLES

### Example 1: Restore a snapshot by using its ID
```
PS C:\> Restore-IscsiVirtualDisk -SnapshotId "{E9A5BA03-85B9-40CA-85DF-DC1695690B40}"
```

This example restores a snapshot with the ID {E9A5BA03-85B9-40CA-85DF-DC1695690B40}.

### Example 2: Restore a snapshot hosted on another computer
```
PS C:\> Restore-IscsiVirtualDisk -SnapshotId "{E9A5BA03-85B9-40CA-85DF-DC1695690B40}" -ComputerName "fs1.contoso.com"
```

This example restores a snapshot with the ID {E9A5BA03-85B9-40CA-85DF-DC1695690B40} hosted on a computer named fs1.contoso.com.

### Example 3: Restore a snapshot by using an input object
```
PS C:\> Restore-IscsiVirtualDisk -InputObject $vhd1snapshot
```

This example uses the **Get-IscsiVirtualDiskSnapshot** cmdlet to retrieve a snapshot, and then assigns the snapshot object to a variable named $vhd1snapshot, and finally passes it to this cmdlet to restore the virtual disk.

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

### -InputObject
Accepts an iSCSI Virtual Disk Snapshot object from the input pipeline.

```yaml
Type: IscsiVirtualDiskSnapshot
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SnapshotId
Specifies the identifier (ID) for the snapshot.

```yaml
Type: String
Parameter Sets: SnapshotId
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

### Microsoft.Iscsi.Target.Commands.IscsiVirtualDiskSnapshot

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Checkpoint-IscsiVirtualDisk](./Checkpoint-IscsiVirtualDisk.md)

[Convert-IscsiVirtualDisk](./Convert-IscsiVirtualDisk.md)

[Get-IscsiVirtualDisk](./Get-IscsiVirtualDisk.md)

[Get-IscsiVirtualDiskSnapshot](./Get-IscsiVirtualDiskSnapshot.md)

[Import-IscsiVirtualDisk](./Import-IscsiVirtualDisk.md)

[New-IscsiVirtualDisk](./New-IscsiVirtualDisk.md)

[Remove-IscsiVirtualDisk](./Remove-IscsiVirtualDisk.md)

[Set-IscsiVirtualDisk](./Set-IscsiVirtualDisk.md)

