---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iscsitarget/get-iscsivirtualdisksnapshot?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IscsiVirtualDiskSnapshot
---

# Get-IscsiVirtualDiskSnapshot

## SYNOPSIS
Gets the properties of the snapshots.

## SYNTAX

### Device (Default)
```
Get-IscsiVirtualDiskSnapshot [[-OriginalPath] <String>] [-ComputerName <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### SnapshotId
```
Get-IscsiVirtualDiskSnapshot [-SnapshotId <String>] [-ComputerName <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-IscsiVirtualDiskSnapshot** cmdlet gets properties of snapshots on a iSCSI virtual disk.

## EXAMPLES

### Example 1: Get all virtual disk snapshots
```
PS C:\> Get-IscsiVirtualDiskSnapshot
```

This example gets all of the virtual disk snapshots on the local server.

### Example 2: Get virtual disk snapshots by ID
```
PS C:\> Get-IscsiVirtualDiskSnapshot -SnapshotId "{E9A5BA03-85B9-40CA-85DF-DC1695690B40}"
```

This example gets all of the virtual disk snapshots with the Id {E9A5BA03-85B9-40CA-85DF-DC1695690B40} on the local server.

### Example 3: Get snapshots for a virtual disk
```
PS C:\> Get-IscsiVirtualDiskSnapshot -Path "E:\temp\test.vhdx"
```

This example gets the snapshots that were taken for the virtual disk E:\temp\test.vhdx.

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

### -OriginalPath
Specifies the path of the virtual hard disk (VHD) file that is associated with the iSCSI virtual disk to which the snapshot belongs.

```yaml
Type: String
Parameter Sets: Device
Aliases: Path

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SnapshotId
Specifies the identifier (ID) for the snapshot.

```yaml
Type: String
Parameter Sets: SnapshotId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Iscsi.Target.Commands.IscsiVirtualDisk

## OUTPUTS

### Microsoft.Iscsi.Target.Commands.IscsiVirtualDiskSnapshot

## NOTES

## RELATED LINKS

[Dismount-IscsiVirtualDiskSnapshot](./Dismount-IscsiVirtualDiskSnapshot.md)

[Export-IscsiVirtualDiskSnapshot](./Export-IscsiVirtualDiskSnapshot.md)

[Mount-IscsiVirtualDiskSnapshot](./Mount-IscsiVirtualDiskSnapshot.md)

[Remove-IscsiVirtualDiskSnapshot](./Remove-IscsiVirtualDiskSnapshot.md)

[Set-IscsiVirtualDiskSnapshot](./Set-IscsiVirtualDiskSnapshot.md)

