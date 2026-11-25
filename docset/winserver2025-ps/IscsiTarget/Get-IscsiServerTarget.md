---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iscsitarget/get-iscsiservertarget?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IscsiServerTarget
---

# Get-IscsiServerTarget

## SYNOPSIS
Obtains iSCSI targets and their associated properties.

## SYNTAX

### Target (Default)
```
Get-IscsiServerTarget [-ClusterGroupName <String>] [[-TargetName] <String>] [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### Device
```
Get-IscsiServerTarget [-ClusterGroupName <String>] [-Path <String>] [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### Initiator
```
Get-IscsiServerTarget [-ClusterGroupName <String>] [-InitiatorId <InitiatorId>] [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IscsiServerTarget** cmdlet obtains iSCSI targets and their associated properties from the local server or specified computer.

## EXAMPLES

### Example 1: Get targets on the local server
```
PS C:\> Get-IscsiServerTarget
```

This example gets the iSCSI targets on the local server.

### Example 2: Get targets on a remote server
```
PS C:\> Get-IscsiServerTarget -ComputerName "fs1.contoso.com"
```

This example gets all of the iSCSI targets on the remote server named fs1.contoso.com.

### Example 3: Get targets on a cluster
```
PS C:\> Get-IscsiServerTarget -ComputerName "fscluster.contoso.com" -ClusterGroupName "target1group"
```

This example gets all of the iSCSI targets in the resource group named target1group on the cluster named fscluster.contoso.com.

### Example 4: Get a target by using a path
```
PS C:\> Get-IscsiServerTarget -Path "E:\temp\test.vhdx"
```

This example gets the iSCSI target associated with the VHD with the path E:\temp\test.vhdx.

### Example 5: Get targets assigned to an initiator
```
PS C:\> Get-IscsiServerTarget -InitiatorId "DNSName:TargetSvr.Contoso.com"
```

This example gets all of the iSCSI targets that have been assigned to the initiator with type DNSName, and value TargetSvr.contoso.com.

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
Use this parameter to filter out the iSCSI Server Target object which can be accessed by the given iSCSI initiator.
The format of this parameter is IdType:Value.
The acceptable values for this parameter are: DNSName, IPAddress, IPv6Address, IQN, and MACAddress.

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
Use this parameter to filter the iSCSI Target object that is associated with the virtual disks.

```yaml
Type: String
Parameter Sets: Device
Aliases: DevicePath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetName
Specifies the name of the iSCSI target.
Use this parameter to filter out the iSCSI Target object.

```yaml
Type: String
Parameter Sets: Target
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Iscsi.Target.Commands.IscsiServerTarget

## OUTPUTS

### Microsoft.Iscsi.Target.Commands.IscsiServerTarget

## NOTES

## RELATED LINKS

[New-IscsiServerTarget](./New-IscsiServerTarget.md)

[Remove-IscsiServerTarget](./Remove-IscsiServerTarget.md)

[Set-IscsiServerTarget](./Set-IscsiServerTarget.md)

