---
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
online version: https://docs.microsoft.com/powershell/module/iscsitarget/new-iscsivirtualdisk?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-IscsiVirtualDisk

## SYNOPSIS
Creates an iSCSI virtual disk with the specified file path and size.

## SYNTAX

### Fixed (Default)
```
New-IscsiVirtualDisk [-Description <String>] [-Path] <String> [-Size] <UInt64> [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### Differencing
```
New-IscsiVirtualDisk [-Description <String>] -ParentPath <String> [-Path] <String> [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **New-IscsiVirtualDisk** cmdlet creates a new iSCSI Virtual Hard Disk (VHD) object with the specified file path and size.
After the iSCSI VHD object has been created, the virtual disk can be assigned to an iSCSI target.
Once a virtual disk has been assigned to a target, and an initiator connects to that target, the iSCSI initiator can then access the virtual disk after the initiator connects to the target.

If the VHD file path does not exist, then a new VHD file will then be created. 

If the VHD file path exists, then the server will return an error.
Use the Import-IscsiVirtualDisk cmdlet to import existing VHDs.

If an error is displayed during the creation of the virtual disk, please check the following conditions: 

 -- An absolute file path must be specified for the **Path** and **ParentPath** parameters. 

 -- The virtual disk file name must have a `.VHD` file extension.
The iSCSI software target does not support the `.VHDX` file extension in this release. 

 -- The VHD file cannot be a network file, or be in a compressed, sparse, or transacted folder.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> New-IscsiVirtualDisk -Path "E:\temp\test.vhd" -Size 10GB
```

This example creates a fixed VHD with 10GB in size.

### EXAMPLE 2
```
PS C:\> New-IscsiVirtualDisk -ParentPath "E:\temp\test.vhd" -Path "E:\temp\child\diff.vhd"
```

This example creates a differencing VHD, with the parent path E:\temp\test.vhd and the differencing VHD path is E:\temp\child\diff.vhd.

### EXAMPLE 3
```
PS C:\> New-IscsiVirtualDisk -Path "E:\temp\test.vhd" -Size 10GB -ComputerName "iscsisvr"
```

This example creates a fixed VHD with the size 10GB at E:\temp\test.vhd on the computer named iscsisvr.

### EXAMPLE 4
```
PS C:\>New-IscsiVirtualDisk -Path ramdisk:test -Size 20MB
```

This example creates a VHD with the size 20MB.
This VHD will not be saved, the VHD will be lost if the wintarget service is restarted or the system is restarted.

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

### -ParentPath
Specifies the parent virtual disk path if the VHD is a differencing disk.

```yaml
Type: String
Parameter Sets: Differencing
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the path of the VHD file that is associated with the iSCSI virtual disk. 

If the VHD file path does not exist, then a new VHD file will then be created. 

If the VHD file path exists, then the server will return an error.
Use the Import-IscsiVirtualDisk cmdlet to import existing VHDs.

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

### -Size
Specifies the size of the iSCSI virtual disk. 
Note: This parameter takes a number and a unit as input, such as 10GB, 20MB, 1TB. 

If this parameter is not provided, then a prompt for the input of this parameter with be displayed, as it is a required field.
At that time, the value will need to be provided in Bytes; since no unit can be entered at the prompt.

```yaml
Type: UInt64
Parameter Sets: Fixed
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Iscsi.Target.Commands.IscsiVirtualDisk

## NOTES

## RELATED LINKS

[Checkpoint-IscsiVirtualDisk](./Checkpoint-IscsiVirtualDisk.md)

[Convert-IscsiVirtualDisk](./Convert-IscsiVirtualDisk.md)

[Expand-IscsiVirtualDisk](./Expand-IscsiVirtualDisk.md)

[Get-IscsiVirtualDisk](./Get-IscsiVirtualDisk.md)

[Import-IscsiVirtualDisk](./Import-IscsiVirtualDisk.md)

[Remove-IscsiVirtualDisk](./Remove-IscsiVirtualDisk.md)

[Restore-IscsiVirtualDisk](./Restore-IscsiVirtualDisk.md)

[Set-IscsiVirtualDisk](./Set-IscsiVirtualDisk.md)

