---
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/iscsitarget/remove-iscsivirtualdisk?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-IscsiVirtualDisk
---

# Remove-IscsiVirtualDisk

## SYNOPSIS
Deletes a Virtual Disk object, without deleting the virtual hard disk (VHD) file.

## SYNTAX

### DevicePath (Default)
```
Remove-IscsiVirtualDisk [-Path] <String> [-ComputerName <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### InputObject
```
Remove-IscsiVirtualDisk -InputObject <IscsiVirtualDisk> [-ComputerName <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-IscsiVirtualDisk** cmdlet deletes the iSCSI Virtual Disk object.
The virtual hard disk (VHD) file is not deleted.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Remove-IscsiVirtualDisk -Path "E:\temp\vhd1.vhdx"
```

This example deletes a virtual disk with the path E:\temp\vhd1.vhdx.

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
Accepts an iSCSI virtual disk object from the input pipeline.

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
Specifies the path of the VHD file that is associated with the iSCSI virtual disk. 
                         
Filter the iSCSI Virtual Disk object using this parameter.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Iscsi.Target.Commands.IscsiVirtualDisk

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Checkpoint-IscsiVirtualDisk](./Checkpoint-IscsiVirtualDisk.md)

[Convert-IscsiVirtualDisk](./Convert-IscsiVirtualDisk.md)

[Get-IscsiVirtualDisk](./Get-IscsiVirtualDisk.md)

[Import-IscsiVirtualDisk](./Import-IscsiVirtualDisk.md)

[New-IscsiVirtualDisk](./New-IscsiVirtualDisk.md)

[Restore-IscsiVirtualDisk](./Restore-IscsiVirtualDisk.md)

[Set-IscsiVirtualDisk](./Set-IscsiVirtualDisk.md)

