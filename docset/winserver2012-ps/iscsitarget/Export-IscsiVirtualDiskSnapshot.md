---
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
online version: https://docs.microsoft.com/powershell/module/iscsitarget/export-iscsivirtualdisksnapshot?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Export-IscsiVirtualDiskSnapshot

## SYNOPSIS
Exports an iSCSI virtual disk snapshot.

## SYNTAX

### SnapshotId (Default)
```
Export-IscsiVirtualDiskSnapshot [-SnapshotId] <String> [-ComputerName <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### InputObject
```
Export-IscsiVirtualDiskSnapshot -InputObject <IscsiVirtualDiskSnapshot> [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Export-IscsiVirtualDiskSnapshot** cmdlet exports a snapshot.
This cmdlet creates a Virtual Disk object and associates the snapshot with it.
Once the Virtual Disk object adds to a target, the initiator can access the snapshot.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Export-IscsiVirtualDiskSnapshot -Snapshot "{E9A5BA03-85B9-40CA-85DF-DC1695690B40}"
```

This example exposes a snapshot with the Id {E9A5BA03-85B9-40CA-85DF-DC1695690B40} as a Virtual Disk object.
To access it, assign the virtual disk with path "\\\\?\GLOBALROOT\Device\HarddiskVolumeShadowCopy{41667F16-0FDD-11E1-BA2A-0010184F53D6}\vhd01" to a target.

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

### Microsoft.Iscsi.Target.Commands.IscsiVirtualDisk

## NOTES

## RELATED LINKS

[Dismount-IscsiVirtualDiskSnapshot](./Dismount-IscsiVirtualDiskSnapshot.md)

[Get-IscsiVirtualDiskSnapshot](./Get-IscsiVirtualDiskSnapshot.md)

[Mount-IscsiVirtualDiskSnapshot](./Mount-IscsiVirtualDiskSnapshot.md)

[Remove-IscsiVirtualDiskSnapshot](./Remove-IscsiVirtualDiskSnapshot.md)

[Set-IscsiVirtualDiskSnapshot](./Set-IscsiVirtualDiskSnapshot.md)

