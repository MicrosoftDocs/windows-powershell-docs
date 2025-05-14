---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iscsitarget/get-iscsivirtualdisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IscsiVirtualDisk
---

# Get-IscsiVirtualDisk

## SYNOPSIS
Obtains the iSCSI virtual disks and their associated properties.

## SYNTAX

### Device (Default)
```
Get-IscsiVirtualDisk [-ClusterGroupName <String>] [[-Path] <String>] [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### Target
```
Get-IscsiVirtualDisk [-ClusterGroupName <String>] [-TargetName <String>] [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### Initiator
```
Get-IscsiVirtualDisk [-ClusterGroupName <String>] [-InitiatorId <InitiatorId>] [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IscsiVirtualDisk** cmdlet obtains the iSCSI virtual disks and their associated properties.

## EXAMPLES

### Example 1: Get all virtual disks on the local server
```
PS C:\> Get-IscsiVirtualDisk
```

This example gets all of the virtual disks on the local server.

### Example 2: Get virtual disk by using a path
```
PS C:\> Get-IscsiVirtualDisk -Path "E:\temp\test.vhdx"
```

This example gets the virtual disk object that has the path E:\temp\test.vhdx on the local server.

### Example 3: Get a virtual disk on a remote server
```
PS C:\> Get-IscsiVirtualDisk -Path "E:\temp\test.vhdx" -ComputerName "fscluster.contoso.com" -ClusterGroupName "target1Group"
```

This example gets the virtual disk object that has the path E:\temp\test.vhdx in the resource group named target1Group on cluster server named fscluster.contoso.com.

### Example 4: Get virtual disks associated with a target
```
PS C:\> Get-IscsiVirtualDisk -TargetName "TargetOne"
```

This example gets all of the virtual disks that are associated with the target named TargetOne on the local server.

### Example 5: Get virtual disks by an initial
```
PS C:\> Get-IscsiVirtualDisk -InitiatorId "IpAddress:10.10.1.1"
```

This example gets all of the virtual disks on the local server that are used by the initiator with IP address 10.10.1.1.

## PARAMETERS

### -ClusterGroupName
Specifies the name of the resource group or network in the resource group on which this cmdlet runs.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -InitiatorId
Specifies the iSCSI initiator identifiers (IDs) to which the iSCSI target is assigned.
Use this parameter to filter out the iSCSI virtual disk object that can be accessed by the given iSCSI initiator.
The format for this parameter is IdType:Value.
The acceptable values for this parameter are: DNSName, IPAddress, IPv6Address, IQN, or MACAddress.

```yaml
Type: InitiatorId
Parameter Sets: Initiator
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the path of the virtual hard disk (VHD) file that is associated with the iSCSI virtual disk.
Filter the iSCSI virtual disk object by using this parameter.

```yaml
Type: String
Parameter Sets: Device
Aliases: DevicePath

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetName
Specifies the name of the iSCSI target.
Use this parameter to filter out the iSCSI virtual disk objects that are assigned to the specified iSCSI target.

```yaml
Type: String
Parameter Sets: Target
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

### None

## OUTPUTS

### Microsoft.Iscsi.Target.Commands.IscsiVirtualDisk

## NOTES

## RELATED LINKS

[Checkpoint-IscsiVirtualDisk](./Checkpoint-IscsiVirtualDisk.md)

[Convert-IscsiVirtualDisk](./Convert-IscsiVirtualDisk.md)

[Import-IscsiVirtualDisk](./Import-IscsiVirtualDisk.md)

[New-IscsiVirtualDisk](./New-IscsiVirtualDisk.md)

[Remove-IscsiVirtualDisk](./Remove-IscsiVirtualDisk.md)

[Restore-IscsiVirtualDisk](./Restore-IscsiVirtualDisk.md)

[Set-IscsiVirtualDisk](./Set-IscsiVirtualDisk.md)

