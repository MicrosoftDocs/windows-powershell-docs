---
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
online version: 
schema: 2.0.0
title: Import-IscsiVirtualDisk
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: B64DA43E-C0A8-48EB-8136-653B2062FEB9
---

# Import-IscsiVirtualDisk

## SYNOPSIS
Adds an iSCSI Virtual Disk object using an existing virtual hard disk (VHD) file.

## SYNTAX

```
Import-IscsiVirtualDisk [-Description <String>] [-Path] <String> [-PassThru] [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Import-IscsiVirtualDisk** cmdlet adds an iSCSI Virtual Disk object using an existing virtual hard disk (VHD) file.
This cmdlet imports virtual disks in both VHD and VHDX formats.
The New-IscsiVirtualDisk cmdlet creates virtual disks in the VHDX format only.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Import-IscsiVirtualDisk -Path "E:\Temp\test.vhd" -Description "Migrated from fs1"
```

This example creates a Virtual Disk object for an existing VHD file located at E:\Temp\test.vhd and sets the Virtual Disk object description to Migrated from fs1.

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
Specifies the description for the iSCSI virtual disk.

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

### -Path
Specifies the path of the VHD file that is associated with the iSCSI virtual disk. 
                         
Filter the iSCSI Virtual Disk object using this parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DevicePath

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

### Microsoft.Iscsi.Target.Commands.IscsiVirtualDisk

## NOTES

## RELATED LINKS

[Checkpoint-IscsiVirtualDisk](./Checkpoint-IscsiVirtualDisk.md)

[Convert-IscsiVirtualDisk](./Convert-IscsiVirtualDisk.md)

[Get-IscsiVirtualDisk](./Get-IscsiVirtualDisk.md)

[New-IscsiVirtualDisk](./New-IscsiVirtualDisk.md)

[Remove-IscsiVirtualDisk](./Remove-IscsiVirtualDisk.md)

[Restore-IscsiVirtualDisk](./Restore-IscsiVirtualDisk.md)

[Set-IscsiVirtualDisk](./Set-IscsiVirtualDisk.md)

