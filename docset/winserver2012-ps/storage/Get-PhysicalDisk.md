---
external help file: Storage2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: A204DCDE-BFAC-43AC-9B79-D81384F255BE
manager: dansimp
---

# Get-PhysicalDisk

## SYNOPSIS
Gets a list of all PhysicalDisk objects visible across any available Storage Management Providers, or optionally a filtered list.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-PhysicalDisk [-AsJob] [-CanPool <Boolean[]>] [-CimSession <CimSession[]>] [-Description <String[]>]
 [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>] [-ThrottleLimit <Int32>]
 [-UniqueId <String[]>] [-Usage <Usage[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-PhysicalDisk [[-FriendlyName] <String[]>] [-AsJob] [-CanPool <Boolean[]>] [-CimSession <CimSession[]>]
 [-Description <String[]>] [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-ThrottleLimit <Int32>] [-Usage <Usage[]>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-PhysicalDisk [-AsJob] [-CanPool <Boolean[]>] [-CimSession <CimSession[]>] [-Description <String[]>]
 [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>] [-StoragePool <CimInstance>]
 [-ThrottleLimit <Int32>] [-Usage <Usage[]>]
```

### UNNAMED_PARAMETER_SET_4
```
Get-PhysicalDisk [-AsJob] [-CanPool <Boolean[]>] [-CimSession <CimSession[]>] [-Description <String[]>]
 [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-StorageSubSystem <CimInstance>] [-ThrottleLimit <Int32>] [-Usage <Usage[]>]
```

### UNNAMED_PARAMETER_SET_5
```
Get-PhysicalDisk [-AsJob] [-CanPool <Boolean[]>] [-CimSession <CimSession[]>] [-Description <String[]>]
 [-HasAllocations <Boolean>] [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-SelectedForUse <Boolean>] [-ThrottleLimit <Int32>] [-Usage <Usage[]>] [-VirtualDisk <CimInstance>]
 [-VirtualRangeMax <UInt64>] [-VirtualRangeMin <UInt64>]
```

## DESCRIPTION
The **Get-PhysicalDisk** cmdlet gets a list of all PhysicalDisk objects visible across any available Storage Management Providers, or optionally a filtered list of disks.

## EXAMPLES

### Example 1: Getting all physical disks
```
PS C:\> Get-PhysicalDisk
FriendlyName        CanPool            OperationalStatus   HealthStatus        Usage                              Size 
------------        --------            -----------------   ------------        -----                              ---- 
PhysicalDisk4       False               OK                  Healthy             Data Store                        25 GB
```

This example returns an array of all PhysicalDisk objects present in the computer.
A storage management provider is required to manage physical disks.

### Example 2: Getting all physical disks eligible for adding to a storage pool
```
PS C:\>Get-PhysicalDisk -CanPool $True
```

This example returns an array of PhysicalDisk objects that are available for adding to a storage pool (they are in a primordial pool).

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

### -CanPool
Gets physical disks that are available for use in a storage pool.

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

### -Description
Gets the physical disks that contain the specified description.
Enter a description, or use wildcard characters to enter a description pattern.

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

### -FriendlyName
Gets the physical disk with the specified friendly name.
Enter a friendly name, or use wildcard characters to enter a name pattern.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HasAllocations


```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HealthStatus
Specifies the **health status** of physical disks.
The acceptable values for this parameter are:

- Healthy 
- Unhealthy 
- Unknown 
- Warning
- 

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

### -Manufacturer
Gets the physical disks with the specified manufacturer.
Enter a manufacturer string, or use wildcard characters to enter a pattern.

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

### -Model
Gets the physical disks of the specified model.
Enter a model string or use wildcard characters to enter a pattern.

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

### -SelectedForUse


```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePool
Accepts a StoragePool object as input and gets the physical disks that belong to the pool.
The Storage Pool CIM object is exposed by the Get-StoragePool cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubSystem
Accepts a StorageSubsystem object as input and gets the physical disks attached to the storage subsystem.
The Storage Subsystem CIM object is exposed by the Get-StorageSubSystem cmdlet.

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
Gets only the physical disks with the specified IDs.
Type one or more IDs (separated by commas), or use wildcard characters to enter a pattern.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Usage
Gets only the physical disks with the specified allocation method (usage) of the disk.
Valid values are AutoSelect, HotSpare, Journal, ManualSelect, Retired, and Unknown.

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

### -VirtualDisk
Accepts a VirtualDisk object as input and gets the physical disks used by the virtual disk.
The VirtualDisk object is exposed by the Get-VirtualDisk cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualRangeMax


```yaml
Type: UInt64
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualRangeMin


```yaml
Type: UInt64
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
You can pipe an MSFT_StoragePool object to the StoragePool parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
You can pipe an MSFT_StorageSubsystem object to the StorageSubsystem parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can pipe an MSFT_VirtualDisk object to the VirtualDisk parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
The Get-PhysicalDisk cmdlet returns objects that represent physical disks.

## NOTES

## RELATED LINKS

[Add-PhysicalDisk](./Add-PhysicalDisk.md)

[Get-StoragePool](./Get-StoragePool.md)

[New-StoragePool](./New-StoragePool.md)

[Remove-PhysicalDisk](./Remove-PhysicalDisk.md)

[Reset-PhysicalDisk](./Reset-PhysicalDisk.md)

[Set-PhysicalDisk](./Set-PhysicalDisk.md)

