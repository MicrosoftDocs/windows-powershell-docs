---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iscsitarget/stop-iscsivirtualdiskoperation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-IscsiVirtualDiskOperation
---

# Stop-IscsiVirtualDiskOperation

## SYNOPSIS
Stops a long-running operation in progress on an iSCSI virtual disk.

## SYNTAX

### DevicePath (Default)
```
Stop-IscsiVirtualDiskOperation [-Path] <String> [-ComputerName <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### InputObject
```
Stop-IscsiVirtualDiskOperation -InputObject <IscsiVirtualDisk> [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-IscsiVirtualDiskOperation** cmdlet stops a long-running operation in progress on an iSCSI virtual disk.
If you cancel an operation, that operation might finish before the cancellation takes effect.
Always re-enumerate or recheck objects affected by an operation after this cmdlet finishes.

Stopping a create operation can remove a created file, or can leave the file intact but not zero it out.

After you stop an operation, the size of an existing file to be increased can appear larger until the next time you restart the iSCSI service, restart the disk, or disable and re-enable the disk.
Some data can be lost.

If you stop an operation, the virtual disk may be in an inconsistent state, and require a new rollback.

This cmdlet accepts values for the *ComputerName* and *Path* parameters by using as pipeline input the *InputObject* parameter.

## EXAMPLES

### Example 1: Stop a virtual disk operation
```
PS C:\> Stop-IscsiVirtualDiskOperation -Path "D:\VirtualDisk09"
```

This command stops an operation in progress on the virtual disk at the specified location.

## PARAMETERS

### -ComputerName
Specifies the computer name, or IP address, of the remote computer, if this cmdlet is run on a remote computer.

Specifies the cluster resource group network name, or cluster node name, if this cmdlet is run on a cluster configuration.

If you do not specify a value for this parameter, the cmdlet uses the local computer.

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
Specifies an **IscsiVirtualDisk** object.
You can get an **IscsiVirtualDisk** object by using the **Get-IscsiVirtualDisk** cmdlet.

```yaml
Type: IscsiVirtualDisk
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path of the virtual hard disk (VHDX) file that is associated with the iSCSI virtual disk.
The cmdlet stops the long-running operation on the iSCSI virtual disk that you specify.

```yaml
Type: String
Parameter Sets: DevicePath
Aliases: DevicePath

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

### None

## NOTES

## RELATED LINKS

[Get-IscsiVirtualDisk](./Get-IscsiVirtualDisk.md)

