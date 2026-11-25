---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iscsitarget/set-iscsivirtualdisksnapshot?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-IscsiVirtualDiskSnapshot
---

# Set-IscsiVirtualDiskSnapshot

## SYNOPSIS
Sets the description for a snapshot.

## SYNTAX

### SnapshotId (Default)
```
Set-IscsiVirtualDiskSnapshot [-SnapshotId] <String> [-Description <String>] [-PassThru]
 [-ComputerName <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

### InputObject
```
Set-IscsiVirtualDiskSnapshot -InputObject <IscsiVirtualDiskSnapshot> [-Description <String>] [-PassThru]
 [-ComputerName <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-IscsiVirtualDiskSnapshot** cmdlet sets the description for a snapshot.

## EXAMPLES

### Example 1: Modify a snapshot description
```
PS C:\> Set-IscsiVirtualDiskSnapshot -SnapshotId "{E9A5BA03-85B9-40CA-85DF-DC1695690B40}" -Description "before upgrade"
```

This example sets a snapshot with the ID {E9A5BA03-85B9-40CA-85DF-DC1695690B40} to have the description before upgrade.

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

### -Description
Specifies the description for the iSCSI virtual disk snapshot.

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

### None

## OUTPUTS

### Microsoft.Iscsi.Target.Commands.IscsiVirtualDiskSnapshot

## NOTES

## RELATED LINKS

[Dismount-IscsiVirtualDiskSnapshot](./Dismount-IscsiVirtualDiskSnapshot.md)

[Export-IscsiVirtualDiskSnapshot](./Export-IscsiVirtualDiskSnapshot.md)

[Get-IscsiVirtualDiskSnapshot](./Get-IscsiVirtualDiskSnapshot.md)

[Mount-IscsiVirtualDiskSnapshot](./Mount-IscsiVirtualDiskSnapshot.md)

[Remove-IscsiVirtualDiskSnapshot](./Remove-IscsiVirtualDiskSnapshot.md)

