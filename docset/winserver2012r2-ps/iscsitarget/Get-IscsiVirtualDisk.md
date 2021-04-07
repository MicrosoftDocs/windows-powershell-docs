---
author: Kateyanne
description: 
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
manager: jasgro
Module Name: IscsiTarget
ms.author: v-kaunu
ms.date: 10/29/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/iscsitarget/get-iscsivirtualdisk?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
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

### EXAMPLE 1
```
PS C:\> Get-IscsiVirtualDisk
```

This example gets all of the virtual disks on the local server.

### EXAMPLE 2
```
PS C:\> Get-IscsiVirtualDisk -Path "E:\temp\test.vhdx"
```

This example gets the virtual disk object with the path E:\temp\test.vhdx on the local server.

### EXAMPLE 3
```
PS C:\> Get-IscsiVirtualDisk -Path "E:\temp\test.vhdx" -ComputerName "fscluster.contoso.com" -ClusterGroupName "target1Group"
```

This example gets the Virtual Disk object with the path E:\temp\test.vhdx in the resource group named target1Group on cluster server named fscluster.contoso.com.

### EXAMPLE 4
```
PS C:\> Get-IscsiVirtualDisk -TargetName "TargetOne"
```

This example gets all of the virtual disks that are associated with the target named TargetOne on the local server.

### EXAMPLE 5
```
PS C:\> Get-IscsiVirtualDisk -InitiatorId "IpAddress:10.10.1.1"
```

This example gets all of the virtual disks on the local server that are used by the initiator with IP address 10.10.1.1.

## PARAMETERS

### -ClusterGroupName
Specifies the name of the resource group or network within the resource group on which this cmdlet should be run.

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
                         
Use this parameter to filter out the iSCSI Virtual Disk object that can be accessed by the given iSCSI initiator. 
                         
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
                         
Filter the iSCSI Virtual Disk object using this parameter.

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
                         
Use this parameter to filter out the iSCSI Virtual Disk object that are assigned to the specified iSCSI target.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

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

