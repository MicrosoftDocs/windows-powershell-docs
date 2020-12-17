---
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
ms.assetid: 790D41BC-782A-4917-8BA5-BD978556479D
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Restore-IscsiVirtualDisk

## SYNOPSIS
Restores an iSCSI virtual disk from a snapshot.

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

### EXAMPLE 1
```
PS C:\> Restore-IscsiVirtualDisk -SnapshotId "{E9A5BA03-85B9-40CA-85DF-DC1695690B40}"
```

This example restores a snapshot with the ID {E9A5BA03-85B9-40CA-85DF-DC1695690B40}.

### EXAMPLE 2
```
PS C:\> Restore-IscsiVirtualDisk -SnapshotId "{E9A5BA03-85B9-40CA-85DF-DC1695690B40}" -ComputerName "fs1.contoso.com"
```

This example restores a snapshot with the ID {E9A5BA03-85B9-40CA-85DF-DC1695690B40} hosted on a computer named fs1.contoso.com.

### EXAMPLE 3
```
PS C:\> Restore-IscsiVirtualDisk -InputObject $vhd1snapshot
```

This example uses the Get-IscsiVirtualDiskSnapshot cmdlet to retrieve a snapshot, then assigns the snapshot object to a variable named $vhd1snapshot, and finally passes it to this cmdlet to restore the virtual disk.

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

### None

## NOTES

## RELATED LINKS

[Checkpoint-IscsiVirtualDisk](./Checkpoint-IscsiVirtualDisk.md)

[Convert-IscsiVirtualDisk](./Convert-IscsiVirtualDisk.md)

[Expand-IscsiVirtualDisk](./Expand-IscsiVirtualDisk.md)

[Get-IscsiVirtualDisk](./Get-IscsiVirtualDisk.md)

[Get-IscsiVirtualDiskSnapshot](./Get-IscsiVirtualDiskSnapshot.md)

[Import-IscsiVirtualDisk](./Import-IscsiVirtualDisk.md)

[New-IscsiVirtualDisk](./New-IscsiVirtualDisk.md)

[Remove-IscsiVirtualDisk](./Remove-IscsiVirtualDisk.md)

[Set-IscsiVirtualDisk](./Set-IscsiVirtualDisk.md)

