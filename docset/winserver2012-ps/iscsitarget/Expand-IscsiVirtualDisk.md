---
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
online version: https://docs.microsoft.com/powershell/module/iscsitarget/expand-iscsivirtualdisk?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Expand-IscsiVirtualDisk

## SYNOPSIS
Expands an iSCSI virtual disk.

## SYNTAX

### Path (Default)
```
Expand-IscsiVirtualDisk [-Path] <String> [-Size] <UInt64> [-PassThru] [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### InputObject
```
Expand-IscsiVirtualDisk -InputObject <IscsiVirtualDisk> [-Size] <UInt64> [-PassThru] [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Expand-IscsiVirtualDisk** cmdlet expands a virtual disk.
When the operation is online, the initiator can still access the virtual disk even while it is expanding. 

However, the initiator will not automatically see the expanded virtual disk.
To get access to the larger virtual disk, the initiator will need to use the Resize-Partition cmdlet to expand the volume hosted on the virtual disk.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Expand-IscsiVirtualDisk -Path "E:\temp\test.vhd" -Size 20GB
```

This example expands the virtual disk with the path E:\temp\test.vhd to 20GB.

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
Accepts an iSCSI Virtual Disk object from the input pipeline.

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
Specifies the path of the virtual hard disk (VHD) file that is associated with the iSCSI virtual disk. 

Filter the iSCSI Virtual Disk object using this parameter.

```yaml
Type: String
Parameter Sets: Path
Aliases: DevicePath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Size
Specifies the size of the expanded iSCSI virtual disk. 
Note: This parameter takes a number and a unit as input, such as 10GB, 20MB, or 1TB. 

If this parameter is not provided, then a prompt for the input of this parameter with be displayed, as it is a required field.
At that time, the value will need to be provided in Bytes; since no unit can be entered at the prompt.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Iscsi.Target.Commands.IscsiVirtualDisk

## OUTPUTS

### Microsoft.Iscsi.Target.Commands.IscsiVirtualDisk

## NOTES

## RELATED LINKS

[Resize-Partition](../storage/Resize-Partition.md)

[Checkpoint-IscsiVirtualDisk](./Checkpoint-IscsiVirtualDisk.md)

[Convert-IscsiVirtualDisk](./Convert-IscsiVirtualDisk.md)

[Get-IscsiVirtualDisk](./Get-IscsiVirtualDisk.md)

[Import-IscsiVirtualDisk](./Import-IscsiVirtualDisk.md)

[New-IscsiVirtualDisk](./New-IscsiVirtualDisk.md)

[Remove-IscsiVirtualDisk](./Remove-IscsiVirtualDisk.md)

[Restore-IscsiVirtualDisk](./Restore-IscsiVirtualDisk.md)

[Set-IscsiVirtualDisk](./Set-IscsiVirtualDisk.md)

