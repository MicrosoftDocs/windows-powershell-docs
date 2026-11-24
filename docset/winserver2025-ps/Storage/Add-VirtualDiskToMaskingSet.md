---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MaskingSet.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/add-virtualdisktomaskingset?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-VirtualDiskToMaskingSet
---

# Add-VirtualDiskToMaskingSet

## SYNOPSIS
Adds a virtual disk to a specified masking set and grants access to the virtual disk to all initiator IDs defined in the masking set.

## SYNTAX

### ByFriendlyName (Default)
```
Add-VirtualDiskToMaskingSet [-MaskingSetFriendlyName] <String[]> [-VirtualDisknames <String[]>]
 [-DeviceNumbers <UInt16[]>] [-DeviceAccesses <DeviceAccess[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByUniqueId
```
Add-VirtualDiskToMaskingSet -MaskingSetUniqueId <String[]> [-VirtualDisknames <String[]>]
 [-DeviceNumbers <UInt16[]>] [-DeviceAccesses <DeviceAccess[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Add-VirtualDiskToMaskingSet -InputObject <CimInstance[]> [-VirtualDisknames <String[]>]
 [-DeviceNumbers <UInt16[]>] [-DeviceAccesses <DeviceAccess[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-VirtualDiskToMaskingSet** cmdlet adds a virtual disk to a specified masking set and grants access to the virtual disk to all initiator IDs defined in the masking set.

ps_storage_spacesubsystem_not_remark

## EXAMPLES

### Example 1: Add a virtual disk to an existing masking set
```
PS C:\> $maskingSet = Get-MaskingSet Cluster1MaskingSet
PS C:\> $virtualDisk = Get-VirtualDisk Volume12
PS C:\> $maskingSet | Add-VirtualDiskToMaskingSet -VirtualDisknames $virtualDisk.Name -DeviceAccesses ReadWrite
```

This example adds the virtual disks named Volume12 to a masking set named Cluster1MaskingSet, and sets the device access to read-write.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceAccesses
Specifies the way in which initiators can access the virtual disk(s) that are part of this masking set.
You must specify a **DeviceAccesses** value for each virtual disk specified by the **VirtualDiskNames** parameter.
Allowed values are NoAccess, ReadOnly, ReadWrite, and Unknown.

```yaml
Type: DeviceAccess[]
Parameter Sets: (All)
Aliases:
Accepted values: Unknown, ReadWrite, ReadOnly, NoAccess

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceNumbers
Specifies the device numbers for one or more virtual disks.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MaskingSetFriendlyName
Specifies the friendly name of the masking set to which you want to add a virtual disk.

```yaml
Type: String[]
Parameter Sets: ByFriendlyName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaskingSetUniqueId
Specifies the UniqueID of the masking set to which you want to add a virtual disk.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Specifies that the cmdlet should output an object representing the masking set to which it added a virtual disk.
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

### -VirtualDisknames
Specifies one or more virtual disk names to add to the masking set.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
You can pipe a **MaskingSet** object to the *InputObject* parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
If you specify the *Passthru* parameter, this cmdlet outputs an object that represents the masking set to which you added a virtual disk.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-MaskingSet](./Get-MaskingSet.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)

