---
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
ms.assetid: 001DF751-A6A3-4983-AC00-A6C3AAF46522
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Mount-IscsiVirtualDiskSnapshot

## SYNOPSIS
Mounts an iSCSI virtual disk snapshot locally.

## SYNTAX

### SnapshotId (Default)
```
Mount-IscsiVirtualDiskSnapshot [-SnapshotId] <String> [-ComputerName <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### InputObject
```
Mount-IscsiVirtualDiskSnapshot -InputObject <IscsiVirtualDiskSnapshot> [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Mount-IscsiVirtualDiskSnapshot** cmdlet mounts a snapshot locally.

Mounting a snapshot locally exposes the snapshot as a disk to the local computer. 

Use diskmgmt.msc or cmdlets to bring the disk online.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Mount-IscsiVirtualDiskSnapshot -SnapshotId "{E9A5BA03-85B9-40CA-85DF-DC1695690B40}"
```

This example mounts the snapshot with the ID {E9A5BA03-85B9-40CA-85DF-DC1695690B40} on the local server, which can be accessed by the backup server to perform backup.

### EXAMPLE 2
```
PS C:\> Mount-IscsiVirtualDiskSnapshot -InputObject $VhdSnapshot
```

This example mounts the Snapshot object stored in a variable named $VhdSnapshot on the local server, which can be accessed by the backup server to perform backup.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Iscsi.Target.Commands.VirtualDiskSnapshot

## OUTPUTS

### Microsoft.Iscsi.Target.Commands.IscsiVirtualDiskSnapshot

## NOTES

## RELATED LINKS

[Dismount-IscsiVirtualDiskSnapshot](./Dismount-IscsiVirtualDiskSnapshot.md)

[Export-IscsiVirtualDiskSnapshot](./Export-IscsiVirtualDiskSnapshot.md)

[Get-IscsiVirtualDiskSnapshot](./Get-IscsiVirtualDiskSnapshot.md)

[Remove-IscsiVirtualDiskSnapshot](./Remove-IscsiVirtualDiskSnapshot.md)

[Set-IscsiVirtualDiskSnapshot](./Set-IscsiVirtualDiskSnapshot.md)

