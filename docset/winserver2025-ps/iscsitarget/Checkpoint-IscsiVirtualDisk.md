---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iscsitarget/checkpoint-iscsivirtualdisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Checkpoint-IscsiVirtualDisk
---

# Checkpoint-IscsiVirtualDisk

## SYNOPSIS
Creates a virtual disk snapshot.

## SYNTAX

```
Checkpoint-IscsiVirtualDisk [-Description <String>] [-OriginalPath] <String> [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Checkpoint-IscsiVirtualDisk** cmdlet creates a snapshot.

## EXAMPLES

### Example 1: Create a snapshot of a VHD
```
PS C:\> Checkpoint-IscsiVirtualDisk -OriginalPath "D:\VHDs\DB.vhdx"
```

This example creates a snapshot of the VHD with the path D:\VHDs\DB.vhdx.

### Example 2: Create a snapshot of a VHD with description
```
PS C:\> Checkpoint-IscsiVirtualDisk -OriginalPath "D:\VHDs\DB.vhdx" -Description "Before database merge" -ComputerName "fssvr.contoso.com"
```

This example creates a snapshot of the VHD with the path D:\VHDs\DB.vhdx, and gives a description of the snapshot.
The operation occurs on a remote computer that has the name fssvr.contoso.com.

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

### -OriginalPath
Specifies the path of the virtual hard disk (VHD) file that is associated with the iSCSI virtual disk to which the snapshot belongs.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Path

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

[Convert-IscsiVirtualDisk](./Convert-IscsiVirtualDisk.md)

[Get-IscsiVirtualDisk](./Get-IscsiVirtualDisk.md)

[Import-IscsiVirtualDisk](./Import-IscsiVirtualDisk.md)

[New-IscsiVirtualDisk](./New-IscsiVirtualDisk.md)

[Remove-IscsiVirtualDisk](./Remove-IscsiVirtualDisk.md)

[Restore-IscsiVirtualDisk](./Restore-IscsiVirtualDisk.md)

[Set-IscsiVirtualDisk](./Set-IscsiVirtualDisk.md)

