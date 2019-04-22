---
external help file: Storage2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: D6192DDC-C09D-4CB3-B406-A1AD801D3DED
manager: dansimp
---

# Add-PhysicalDisk

## SYNOPSIS
Adds a physical disk to the specified storage pool or manually assigns a physical disk to a specific virtual disk.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-PhysicalDisk [[-VirtualDisk] <CimInstance>] [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-VirtualDiskFriendlyName <String>] [-VirtualDiskName <String>] [-VirtualDiskUniqueId <String>]
 -PhysicalDisks <CimInstance[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Add-PhysicalDisk [[-StoragePool] <CimInstance>] [-AsJob] [-CimSession <CimSession[]>]
 [-StoragePoolFriendlyName <String>] [-StoragePoolName <String>] [-StoragePoolUniqueId <String>]
 [-ThrottleLimit <Int32>] [-Usage <Usage>] -PhysicalDisks <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-PhysicalDisk** cmdlet adds a physical disk to the specified storage pool.
The cmdlet can also assign a ManualSelect physical disk already in the storage pool to a specific virtual disk.

## EXAMPLES

### Example 1: Adding a physical disk by storage pool friendly name
```
PS C:\>$PDToAdd = Get-PhysicalDisk -FriendlyName PhysicalDisk5 PS C:\>Add-PhysicalDisk -PhysicalDisks $PDToAdd -StoragePoolFriendlyName CompanyData
```

This example gets the PhysicalDisk object for the physical disk named PhysicalDisk5 and assigns it to the $PDToAdd variable.
It then adds the PhysicalDisk object to the storage pool named CompanyData.

### Example 2: Adding all available physical disks
```
PS C:\>$PDToAdd = Get-PhysicalDisk -CanPool $True PS C:\>Add-PhysicalDisk -StoragePoolFriendlyName "Demo Pool" -PhysicalDisks $PDToAdd
```

This example gets all PhysicalDisk objects that can be added to a storage pool and assigns them to the $PDToAdd variable.
It then adds the available physical disks to the storage pool named Demo Pool.

### Example 3: Piping a storage pool to Add-PhysicalDisk
```
PS C:\>Get-StoragePool -IsPrimordial $False | Add-PhysicalDisk -PhysicalDisks (Get-PhysicalDisk -CanPool $True)
```

This example gets all storage pools (except primordial pools) and pipes the output to the Add-PhysicalDisk cmdlet (this will not work if you created more than one storage pool).
This example then uses the Get-Physical Disk cmdlet inside of parentheses to specify all available physical disks without using variables.

### Example 4: Manually assigning physical disks to a virtual disk
```
PS C:\>Add-PhysicalDisk -VirtualDiskFriendlyName UserData -PhysicalDisks (Get-PhysicalDisk -FriendlyName PhysicalDisk3, PhysicalDisk4)
```

This example gets two physical disks that have already been added to the storage pool and designated as ManualSelect disks, PhysicalDisk3 and PhysicalDisk4, and assigns them to the virtual disk UserData.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -PhysicalDisks
Specifies the physical disk objects to add to the storage pool.
Enter one or more PhysicalDisk CIM objects.

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePool
Specifies the storage pool object to which you want to add the physical disk(s).
Enter a StoragePool CIM object.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StoragePoolFriendlyName
Specifies the friendly name of the storage pool to which you want to add the physical disk.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePoolName
Specifies the name of the storage pool, provided by the Storage Management Provider, to which you want to add the physical disk.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePoolUniqueId
Specifies the ID of the storage pool to which you want to add the physical disk.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
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

### -Usage
Specifies the allocation method (usage) for the disk.
Valid values are AutoSelect, HotSpare, Journal, ManualSelect, Retired, and Unknown.

```yaml
Type: Usage
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDisk
Specifies the virtual disk object to which to exclusively assign the physical disk(s).
Enter one or more VirtualDisk CIM objects.

Note:   To manually assign a physical disk to a virtual disk, first add the physical disk to the appropriate pool and set the Usage property on the disk to ManualSelect.
You can do so by using the Add-PhysicalDisk or Set-PhysicalDisk cmdlets.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualDiskFriendlyName
Specifies the friendly name of the virtual disk to which to exclusively assign the physical disk(s)

Note:   To manually assign a physical disk to a virtual disk, first add the physical disk to the appropriate pool and set the Usage property on the disk to ManualSelect.
You can do so by using the Add-PhysicalDisk or Set-PhysicalDisk cmdlets.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDiskName
Specifies the name of the virtual disk to which to exclusively assign the physical disk(s)

Note:   To manually assign a physical disk to a virtual disk, first add the physical disk to the appropriate pool and set the Usage property on the disk to ManualSelect.
You can do so by using the Add-PhysicalDisk or Set-PhysicalDisk cmdlets.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDiskUniqueId
Specifies the ID of the virtual disk to which to exclusively assign the physical disk(s)

Note:   To manually assign a physical disk to a virtual disk, first add the physical disk to the appropriate pool and set the Usage property on the disk to ManualSelect.
You can do so by using the Add-PhysicalDisk or Set-PhysicalDisk cmdlets.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
You can pipe an MSFT_StoragePool object to the StoragePool parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can pipe an MSFT_VirtualDisk object to the VirtualDisk parameter.

## OUTPUTS

## NOTES

## RELATED LINKS

[Where-Object](http://go.microsoft.com/fwlink/p/?LinkID=113423)

[Get-PhysicalDisk](./Get-PhysicalDisk.md)

[Remove-PhysicalDisk](./Remove-PhysicalDisk.md)

[Reset-PhysicalDisk](./Reset-PhysicalDisk.md)

[Set-PhysicalDisk](./Set-PhysicalDisk.md)

