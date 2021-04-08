---
author: Kateyanne
external help file: Storage2_Cmdlets.xml
manager: dansimp
Module Name: Storage
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/storage/get-storagesubsystem?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-StorageSubsystem

## SYNOPSIS
Gets one or more StorageSubsystem objects.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-StorageSubsystem [[-FriendlyName] <String[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-StorageSubsystem [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-Manufacturer <String[]>] [-Model <String[]>] [-ThrottleLimit <Int32>] [-VirtualDisk <CimInstance>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-StorageSubsystem [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-Manufacturer <String[]>] [-Model <String[]>] [-PhysicalDisk <CimInstance>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_4
```
Get-StorageSubsystem [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-Manufacturer <String[]>] [-Model <String[]>] [-OffloadDataTransferSetting <CimInstance>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_5
```
Get-StorageSubsystem [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-Manufacturer <String[]>] [-Model <String[]>] [-ThrottleLimit <Int32>] [-UniqueId <String[]>]
```

### UNNAMED_PARAMETER_SET_6
```
Get-StorageSubsystem [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-Manufacturer <String[]>] [-Model <String[]>] [-TargetPortal <CimInstance>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_7
```
Get-StorageSubsystem [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-Manufacturer <String[]>] [-Model <String[]>] [-TargetPort <CimInstance>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_8
```
Get-StorageSubsystem [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-Manufacturer <String[]>] [-MaskingSet <CimInstance>] [-Model <String[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_9
```
Get-StorageSubsystem [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-InitiatorId <CimInstance>] [-Manufacturer <String[]>] [-Model <String[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_10
```
Get-StorageSubsystem [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-Manufacturer <String[]>] [-Model <String[]>] [-StoragePool <CimInstance>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_11
```
Get-StorageSubsystem [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-Manufacturer <String[]>] [-Model <String[]>] [-StorageProvider <CimInstance>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_12
```
Get-StorageSubsystem [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-Manufacturer <String[]>] [-Model <String[]>] [-Name <String[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-StorageSubsystem** cmdlet gets one or more StorageSubsystem objects.
If no parameters are specified, then all subsystems on the system will be returned.
If two parameters are specified that conflict with unique values, then no subsystem will be returned; since none match that criteria.

## EXAMPLES

### Example 1: Get all storage subsystems
```
PS C:\>Get-StorageSubsystem
```

This example returns a list of all visible StorageSubsystem objects across all accessible StorageProvider objects.

### Example 2: Get the Storage Spaces subsystem
```
PS C:\>Get-StorageSubSystem -Model "Storage Spaces"
FriendlyName                            HealthStatus                            OperationalStatus

------------                            ------------                            -----------------

Storage Spaces on SRV1                  Healthy                                 OK
```

This example returns only the StorageSubsystem object for the Storage Spaces provider.

### Example 3: Get all unhealthy storage subsystems
```
PS C:\>Get-StorageSubSystem -HealthStatus Unhealthy
```

This example gets all storage subsystems in an unhealthy state.

### Example 4: Get storage subsystems that have SMPs that support ODX
```
PS C:\>Get-OffloadDataTransferSetting | Get-StorageSubSystem
```

This example displays all storage subsystems on storage management providers that support Windows Offloaded Data Transfers (ODX).
Storage arrays that support ODX using the SMI-S protocol are not shown.

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

### -FriendlyName
Specifies the friendly name of the storage subsystem to get.

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
Gets all storage subsystems that have the specified health status.
Acceptable values are Healthy, Warning, and Unhealthy.

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
Gets the storage subsystem associated with the specified InitiatorId object.
Enter an InitiatorID CIM object.
The InitiatorID object is exposed by the Get-InitiatorId cmdlet.

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

### -Manufacturer
Gets StorageSubsystem objects with the specified manufacturer name.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -MaskingSet
Gets the StorageSubsystem for the specified MaskingSet object.
Enter a MaskingSet CIM object.
The MaskingSet object is exposed by the Get-MaskingSet cmdlet.

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

### -Model
Gets the StorageSubsystem with the specified model string.

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

### -Name
Gets the StorageSubsystem with the specified name.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_12
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OffloadDataTransferSetting
Gets the StorageSubsystem associated with the specified OffloadDataTransferSetting object.
The Offload Data Transfer Setting CIM object is exposed by the Get-OffloadDataTransferSetting cmdlet.

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

### -PhysicalDisk
Gets the StorageSubsystem associated with the specified PhysicalDisk object.
The Physical Disk CIM object is exposed by the Get-PhysicalDisk cmdlet.

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

### -StoragePool
Gets the StorageSubsystem associated with the specified StoragePool object.
The Storage Pool CIM object is exposed by the Get-StoragePool cmdlet.

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

### -StorageProvider
Gets the StorageSubsystem associated with the specified StorageProvider object.
The Storage Provider CIM object is exposed by the Get-StorageProvider cmdlet.

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

### -TargetPort
Gets the StorageSubsystem associated with the specified TargetPort object.
object as input.
The TargetPort CIM object is exposed by the Get-TargetPort cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_7
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetPortal
Gets the StorageSubsystem associated with the specified TargetPortal object.
object as input.
The TargetPortal CIM object is exposed by the Get-TargetPortal cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_6
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
Gets the StorageSubsystem with the specified UniqueID value.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualDisk
Gets the StorageSubsystem associated with the specified VirtualDisk object.
object as input.
The Virtual Disk CIM object is exposed by the Get-VirtualDisk cmdlet.

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

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_InitiatorId
You can pipe an InitiatorID object to the **InitiatorID** parameter to get the storage subsystem associated with the object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
You can pipe a MaskingSet object to the **MaskingSet** parameter to get the storage subsystem associated with the object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_OffloadDataTransferSetting
You can pipe an OffloadDataTransferSetting object to the **OffloadDataTransferSetting** parameter to get the storage subsystem associated with the object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
You can pipe a PhysicalDisk object to the **PhysicalDisk** parameter to get the storage subsystem associated with the object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
You can pipe a StoragePool object to the **StoragePool** parameter to get the storage subsystem associated with the object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageProvider
You can pipe a StorageProvider object to the **StorageProvider** parameter to get the storage subsystem associated with the object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_TargetPort
You can pipe a TargetPort object to the **TargetPort** parameter to get the storage subsystem associated with the object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can pipe a VirtualDisk object to the **VirtualDisk** parameter to get the storage subsystem associated with the object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
This cmdlet outputs an object representing a storage subsystem.

## NOTES

## RELATED LINKS

[Get-StorageProvider](./Get-StorageProvider.md)

[Set-StorageSubsystem](./Set-StorageSubsystem.md)

