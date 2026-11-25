---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageCmdlets.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/set-physicaldisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PhysicalDisk
---

# Set-PhysicalDisk

## SYNOPSIS
Sets attributes on a specific physical disk.

## SYNTAX

### ByUniqueId (Default)
```
Set-PhysicalDisk [-NewFriendlyName <String>] [-Description <String>] [-Usage <Usage>] [-MediaType <MediaType>]
 -UniqueId <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObject
```
Set-PhysicalDisk -InputObject <CimInstance[]> [-NewFriendlyName <String>] [-Description <String>]
 [-Usage <Usage>] [-MediaType <MediaType>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByFriendlyName
```
Set-PhysicalDisk [-NewFriendlyName <String>] [-Description <String>] [-Usage <Usage>] [-MediaType <MediaType>]
 [-FriendlyName] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Set-PhysicalDisk** cmdlet sets attributes on a specific physical disk in a storage pool, other than the primordial pool when using Storage Spaces.

When using the Windows Storage subsystem, this cmdlet only works on physical disks that have been added to a storage pool.

## EXAMPLES

### Example 1: Change the friendly name of a physical disk
```
PS C:\>Set-PhysicalDisk -FriendlyName "PhysicalDisk4" -NewFriendlyName "PhysicalDiskInSlot5"
```

This example changes the friendly name of PhysicalDisk4 to PhysicalDiskInSlot5.

### Example 2: Change the Usage of a physical disk
```
PS C:\>Set-PhysicalDisk -FriendlyName PhysicalDisk2 -Usage AutoSelect
```

This example changes the Usage property of PhysicalDisk2 to AutoSelect.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Sets the description of the specified physical disk.

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

### -FriendlyName
Specifies the friendly name of the physical disk on which to set attributes.

```yaml
Type: String
Parameter Sets: ByFriendlyName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: ByObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MediaType
Specifies a media type.
The cmdlet changes the media type that is associated with physical disk to the media type that you specify.
The acceptable values for this parameter are:

- SSD
- HDD

```yaml
Type: MediaType
Parameter Sets: (All)
Aliases:
Accepted values: HDD, SSD, SCM

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewFriendlyName
Specifies the new friendly name of the physical disk.

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

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UniqueId
Specifies the UniqueID of the physical disk on which to set attributes.

```yaml
Type: String
Parameter Sets: ByUniqueId
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Usage
Specifies the allocation method (usage) for the disk.
Valid values are AutoSelect, HotSpare, Journal, ManualSelect, Retired, and Unknown.

```yaml
Type: Usage
Parameter Sets: (All)
Aliases:
Accepted values: AutoSelect, ManualSelect, HotSpare, Retired, Journal

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
You can use the pipeline operator to pass an MSFT_PhysicalDisk object to the *InputObject* parameter.

## OUTPUTS

### None

## NOTES
* When using the Windows Storage subsystem, this cmdlet works only on physical disks that have been added to a storage pool.
* The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).s

## RELATED LINKS

[Add-PhysicalDisk](./Add-PhysicalDisk.md)

[Get-PhysicalDisk](./Get-PhysicalDisk.md)

[Remove-PhysicalDisk](./Remove-PhysicalDisk.md)

[Reset-PhysicalDisk](./Reset-PhysicalDisk.md)

