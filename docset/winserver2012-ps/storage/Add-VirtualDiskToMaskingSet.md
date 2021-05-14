---
external help file: Storage2_Cmdlets.xml
Module Name: Storage
online version: https://docs.microsoft.com/powershell/module/storage/add-virtualdisktomaskingset?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-VirtualDiskToMaskingSet

## SYNOPSIS
Adds a virtual disk to a specified masking set and grants access to the virtual disk to all initiator IDs defined in the masking set.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-VirtualDiskToMaskingSet [-MaskingSetFriendlyName] <String[]> [-AsJob] [-CimSession <CimSession[]>]
 [-DeviceAccesses <DeviceAccess[]>] [-DeviceNumbers <UInt16[]>] [-PassThru] [-ThrottleLimit <Int32>]
 [-VirtualDisknames <String[]>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Add-VirtualDiskToMaskingSet [-AsJob] [-CimSession <CimSession[]>] [-DeviceAccesses <DeviceAccess[]>]
 [-DeviceNumbers <UInt16[]>] [-PassThru] [-ThrottleLimit <Int32>] [-VirtualDisknames <String[]>]
 -MaskingSetUniqueId <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Add-VirtualDiskToMaskingSet [-AsJob] [-CimSession <CimSession[]>] [-DeviceAccesses <DeviceAccess[]>]
 [-DeviceNumbers <UInt16[]>] [-PassThru] [-ThrottleLimit <Int32>] [-VirtualDisknames <String[]>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-VirtualDiskToMaskingSet** cmdlet adds a virtual disk to a specified masking set and grants access to the virtual disk to all initiator IDs defined in the masking set.

ps_storage_spacesubsystem_not_remark

## EXAMPLES

### Example 1: Add a virtual disk to an existing masking set
```
PS C:\>$maskingSet = Get-MaskingSet Cluster1MaskingSet PS C:\>$virtualDisk = Get-VirtualDisk Volume12 PS C:\>$maskingSet | Add-VirtualDiskToMaskingSet -VirtualDisknames $virtualDisk.Name -DeviceAccesses ReadWrite
```

This example adds the virtual disks named Volume12 to a masking set named Cluster1MaskingSet, and sets the device access to read-write.

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

### -DeviceAccesses
Specifies the way in which initiators can access the virtual disk(s) that are part of this masking set.
You must specify a **DeviceAccesses** value for each virtual disk specified by the **VirtualDiskNames** parameter.
Allowed values are NoAccess, ReadOnly, ReadWrite, and Unknown

```yaml
Type: DeviceAccess[]
Parameter Sets: (All)
Aliases: 

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
Specifies the MaskingSet object to which you want to a virtual disk.
Specify a MaskingSet CIM object, which are output by the Get-MaskingSet and New-MaskingSet cmdlets.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaskingSetUniqueId
Specifies an UniqueID of the masking set to which you want to add a virtual disk.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Specifies one or more virtual disk names that are to be added to the masking set.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
You can pipe a MaskingSet object to the **InputObject** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
If you specify the **Passthru** parameter, this cmdlet outputs an object that represents the masking set to which you added a virtual disk.

## NOTES

## RELATED LINKS

[Get-MaskingSet](./Get-MaskingSet.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)

