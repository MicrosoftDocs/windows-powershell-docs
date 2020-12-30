---
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
online version: 
schema: 2.0.0
title: Checkpoint-IscsiVirtualDisk
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 6854D819-70B6-488B-A2C6-6001BBCBD344
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

### EXAMPLE 1
```
PS C:\> Checkpoint-IscsiVirtualDisk -OriginalPath "D:\VHDs\DB.vhdx"
```

This example creates a snapshot of the VHD with the path D:\VHDs\DB.vhdx.

### EXAMPLE 2
```
PS C:\> Checkpoint-IscsiVirtualDisk -OriginalPath "D:\VHDs\DB.vhdx" -Description "Before database merge" -ComputerName "fssvr.contoso.com"
```

This example creates a snapshot of the VHD with the path D:\VHDs\DB.vhdx, and gives a description of the snapshot.
The operation will take place on a remote computer with the name fssvr.contoso.com.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

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

