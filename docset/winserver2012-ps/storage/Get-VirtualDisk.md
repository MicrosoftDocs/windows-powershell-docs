---
author: Kateyanne
external help file: Storage2_Cmdlets.xml
manager: dansimp
Module Name: Storage
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/storage/get-virtualdisk?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VirtualDisk

## SYNOPSIS
Returns a list of VirtualDisk objects, across all storage pools, across all providers, or optionally a filtered subset based on provided criteria.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VirtualDisk [[-FriendlyName] <String[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-HealthStatus <HealthStatus[]>] [-IsSnapshot <Boolean[]>] [-OtherUsageDescription <String[]>]
 [-ThrottleLimit <Int32>] [-Usage <Usage[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VirtualDisk [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsSnapshot <Boolean[]>] [-OtherUsageDescription <String[]>] [-TargetPort <CimInstance>]
 [-ThrottleLimit <Int32>] [-Usage <Usage[]>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-VirtualDisk [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsSnapshot <Boolean[]>] [-OtherUsageDescription <String[]>] [-ThrottleLimit <Int32>] [-UniqueId <String[]>]
 [-Usage <Usage[]>]
```

### UNNAMED_PARAMETER_SET_4
```
Get-VirtualDisk [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-InitiatorId <CimInstance>] [-IsSnapshot <Boolean[]>] [-OtherUsageDescription <String[]>]
 [-ThrottleLimit <Int32>] [-Usage <Usage[]>]
```

### UNNAMED_PARAMETER_SET_5
```
Get-VirtualDisk [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsSnapshot <Boolean[]>] [-Name <String[]>] [-OtherUsageDescription <String[]>] [-ThrottleLimit <Int32>]
 [-Usage <Usage[]>]
```

### UNNAMED_PARAMETER_SET_6
```
Get-VirtualDisk [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsSnapshot <Boolean[]>] [-OtherUsageDescription <String[]>] [-TargetVirtualDisk <CimInstance>]
 [-ThrottleLimit <Int32>] [-Usage <Usage[]>]
```

### UNNAMED_PARAMETER_SET_7
```
Get-VirtualDisk [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsSnapshot <Boolean[]>] [-OtherUsageDescription <String[]>] [-SourceVirtualDisk <CimInstance>]
 [-ThrottleLimit <Int32>] [-Usage <Usage[]>]
```

### UNNAMED_PARAMETER_SET_8
```
Get-VirtualDisk [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsSnapshot <Boolean[]>] [-MaskingSet <CimInstance>] [-OtherUsageDescription <String[]>]
 [-ThrottleLimit <Int32>] [-Usage <Usage[]>]
```

### UNNAMED_PARAMETER_SET_9
```
Get-VirtualDisk [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-InitiatorPort <CimInstance>] [-IsSnapshot <Boolean[]>] [-OtherUsageDescription <String[]>]
 [-ThrottleLimit <Int32>] [-Usage <Usage[]>]
```

### UNNAMED_PARAMETER_SET_10
```
Get-VirtualDisk [-AsJob] [-CimSession <CimSession[]>] [-Disk <CimInstance>] [-HealthStatus <HealthStatus[]>]
 [-IsSnapshot <Boolean[]>] [-OtherUsageDescription <String[]>] [-ThrottleLimit <Int32>] [-Usage <Usage[]>]
```

### UNNAMED_PARAMETER_SET_11
```
Get-VirtualDisk [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsSnapshot <Boolean[]>] [-OtherUsageDescription <String[]>] [-PhysicalDisk <CimInstance>]
 [-PhysicalRangeMax <UInt64>] [-PhysicalRangeMin <UInt64>] [-ThrottleLimit <Int32>] [-Usage <Usage[]>]
```

### UNNAMED_PARAMETER_SET_12
```
Get-VirtualDisk [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsSnapshot <Boolean[]>] [-OtherUsageDescription <String[]>] [-StoragePool <CimInstance>]
 [-ThrottleLimit <Int32>] [-Usage <Usage[]>]
```

### UNNAMED_PARAMETER_SET_13
```
Get-VirtualDisk [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsSnapshot <Boolean[]>] [-OtherUsageDescription <String[]>] [-StorageSubSystem <CimInstance>]
 [-ThrottleLimit <Int32>] [-Usage <Usage[]>]
```

## DESCRIPTION
The **Get-VirtualDisk** cmdlet returns a list of VirtualDisk objects, across all storage pools, across all providers, or optionally a filtered subset based on provided criteria.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-VirtualDisk
```

This example returns all VirtualDisk objects across all visible StoragePool objects, across all visible StorageProvider objects.

### EXAMPLE 2
```
PS C:\>$stpool = (Get-StoragePool -FriendlyName "SpacesPool")



PS C:\>Get-VirtualDisk -StoragePool $stpool
```

This example lists only the virtual disks from the StoragePool object named SpacesPool.

### EXAMPLE 3
```
PS C:\>Get-VirtualDisk | Where-Object -FilterScript {$_.HealthStatus -Ne "Healthy"}
```

This example lists all virtual disks, across all pools, and all providers, which are not currently in a healthy state.

### EXAMPLE 4
```
PS C:\>$part = (Get-Partition -DriveLetter Y)



PS C:\>Get-VirtualDisk -Partition $part
```

This example gets the virtual disk associated with the partition with drive letter Y.

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

### -Disk
Accepts a Disk object as input.
The Disk CIM object is exposed by the Get-Diskhttp://technet.microsoft.com/library/3929eb27-1365-42ca-8acf-68b364c3599f cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_10
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -FriendlyName
Specifies a friendly name for a disk.
The friendly name may be defined by a user and is not guaranteed to be unique.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HealthStatus
Specifies the status of an object and indicates if the object is **Healthy** or **Warning Unhealthy**.

```yaml
Type: HealthStatus[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitiatorId
Accepts an InitiatorId object as input.
The Initiator ID CIM object is exposed by the Get-InitiatorIdhttp://technet.microsoft.com/library/56c96b69-33c0-402b-8813-d64a4434011d cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InitiatorPort
Accepts an InitiatorPort object as input.
The Initiator Port CIM object is exposed by the Get-InitiatorPorthttp://technet.microsoft.com/library/580a19cf-26d1-45bb-ad34-a6265e2efacf cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_9
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsSnapshot
Specifies that the virtual disk is a snapshot of another virtual disk.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaskingSet
Accepts a MaskingSet object as input.
The Masking Set CIM object is exposed by the Get-MaskingSethttp://technet.microsoft.com/library/a7ef71fd-f7f6-4231-8799-0e96dd9eac84 cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_8
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of an object or setting.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OtherUsageDescription
Specifies the usage of this object.

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

### -PhysicalDisk
Accepts a PhysicalDisk object as input.
The Physical Disk CIM object is exposed by the Get-PhysicalDiskhttp://technet.microsoft.com/library/a204dcde-bfac-43ac-9b79-d81384f255be cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_11
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PhysicalRangeMax


```yaml
Type: UInt64
Parameter Sets: UNNAMED_PARAMETER_SET_11
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalRangeMin


```yaml
Type: UInt64
Parameter Sets: UNNAMED_PARAMETER_SET_11
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceVirtualDisk


```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_7
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePool
Accepts a StoragePool object as input.
The Storage Pool CIM object is exposed by the Get-StoragePoolhttp://technet.microsoft.com/library/288acad9-7678-45c2-b7b4-3a0522fea499 cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_12
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubSystem
Accepts a StorageSubsystem object as input.
The Storage Subsystem CIM object is exposed by the Get-StorageSubsystemhttp://technet.microsoft.com/library/ea364a0b-06d6-4653-b41c-be69b8038b54 cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_13
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetPort
Accepts a TargetPort object as input.
The Target Port CIM object is exposed by the Get-TargetPorthttp://technet.microsoft.com/library/4c139739-cda3-4379-b87b-60b1b4db8cd2 cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetVirtualDisk


```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_6
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
Specifies an ID used to uniquely identify a Disk object in the system.
The ID persists through restarts.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Usage
Indicates the intended usage of the virtual disk.

```yaml
Type: Usage[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Disk
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_InitiatorId
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_InitiatorPort
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partition
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_TargetPort
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/?LinkID=113423)

[Connect-VirtualDisk](./Connect-VirtualDisk.md)

[Disconnect-VirtualDisk](./Disconnect-VirtualDisk.md)

[Get-Partition](./Get-Partition.md)

[Get-StoragePool](./Get-StoragePool.md)

[Hide-VirtualDisk](./Hide-VirtualDisk.md)

[New-VirtualDisk](./New-VirtualDisk.md)

[Remove-VirtualDisk](./Remove-VirtualDisk.md)

[Repair-VirtualDisk](./Repair-VirtualDisk.md)

[Resize-VirtualDisk](./Resize-VirtualDisk.md)

[Set-VirtualDisk](./Set-VirtualDisk.md)

[Show-VirtualDisk](./Show-VirtualDisk.md)

