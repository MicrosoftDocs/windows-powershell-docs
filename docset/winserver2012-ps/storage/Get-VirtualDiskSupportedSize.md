---
external help file: Storage2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: B0046458-D023-444D-A17D-4A4BCB10AC5D
manager: dansimp
---

# Get-VirtualDiskSupportedSize

## SYNOPSIS
Returns all sizes supported by a storage pool for virtual disk creation based on the specified resiliency setting name.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VirtualDiskSupportedSize [[-FriendlyName] <String[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-HealthStatus <HealthStatus[]>] [-IsPrimordial <Boolean[]>] [-ResiliencySettingName <String>]
 [-ThrottleLimit <Int32>] [-Usage <Usage[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VirtualDiskSupportedSize [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsPrimordial <Boolean[]>] [-PhysicalDisk <CimInstance>] [-ResiliencySettingName <String>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-VirtualDiskSupportedSize [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsPrimordial <Boolean[]>] [-ResiliencySettingName <String>] [-StorageSubSystem <CimInstance>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_4
```
Get-VirtualDiskSupportedSize [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsPrimordial <Boolean[]>] [-OtherUsageDescription <String[]>] [-ResiliencySettingName <String>]
 [-ThrottleLimit <Int32>] [-Usage <Usage[]>]
```

### UNNAMED_PARAMETER_SET_5
```
Get-VirtualDiskSupportedSize [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsPrimordial <Boolean[]>] [-Name <String[]>] [-ResiliencySettingName <String>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_6
```
Get-VirtualDiskSupportedSize [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsPrimordial <Boolean[]>] [-ResiliencySettingName <String>] [-ThrottleLimit <Int32>] [-UniqueId <String[]>]
```

### UNNAMED_PARAMETER_SET_7
```
Get-VirtualDiskSupportedSize [-AsJob] [-CimSession <CimSession[]>] [-ResiliencySettingName <String>]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]>
```

### UNNAMED_PARAMETER_SET_8
```
Get-VirtualDiskSupportedSize [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsPrimordial <Boolean[]>] [-ResiliencySetting <CimInstance>] [-ResiliencySettingName <String>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_9
```
Get-VirtualDiskSupportedSize [-AsJob] [-CimSession <CimSession[]>] [-HealthStatus <HealthStatus[]>]
 [-IsPrimordial <Boolean[]>] [-ResiliencySettingName <String>] [-ThrottleLimit <Int32>]
 [-VirtualDisk <CimInstance>]
```

## DESCRIPTION
The **Get-VirtualDiskSupportedSize** cmdlet returns all sizes supported by a storage pool for virtual disk creation based on the specified resiliency setting name.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-VirtualDiskSupportedSize -ResiliencySettingsName Mirror
```

This example lists the minimum and maximum supported sizes for virtual disk creation using the specified resiliency settings name.

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
Specifies a friendly name for a storage pool.
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_8, UNNAMED_PARAMETER_SET_9
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Accepts an object from the pipeline as input.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_7
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsPrimordial
Specifies that the storage pool is a Primordial pool.
Multiple Primordial pools are possible with some Storage Management providers.

```yaml
Type: Boolean[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_8, UNNAMED_PARAMETER_SET_9
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PhysicalDisk
Accepts a PhysicalDisk object as input.
The Physical Disk CIM object is exposed by the Get-PhysicalDiskhttp://technet.microsoft.com/library/a204dcde-bfac-43ac-9b79-d81384f255be cmdlet.

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

### -ResiliencySetting
Accepts a ResiliencySetting object as input.
The Resiliency Setting CIM object is exposed by the com/library/ea364a0b-06d6-4653-b41c-be69b8038b54" \t "_blank" Get-ResiliencySetting cmdlet.

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

### -ResiliencySettingName
Specifies the name of the desired resiliency setting, for example **Simple**, **Mirror**, or **Parity**.

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

### -StorageSubSystem
Accepts a StorageSubsystem object as input.
The Storage Subsystem CIM object is exposed by the Get-StorageSubsystemhttp://technet.microsoft.com/library/ea364a0b-06d6-4653-b41c-be69b8038b54 cmdlet.

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
Parameter Sets: UNNAMED_PARAMETER_SET_6
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Usage
Specifies the intended usage.

```yaml
Type: Usage[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualDisk
Accepts a VirtualDisk object as input.
The Virtual Disk CIM object is exposed by the Get-VirtualDiskhttp://technet.microsoft.com/library/0eeba53f-6468-485f-a680-49260b4c83f0 cmdlet.

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

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_ResiliencySetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### System.UInt64[]

### System.UInt64

## NOTES

## RELATED LINKS

[Get-ResiliencySetting](./Get-ResiliencySetting.md)

[New-VirtualDisk](./New-VirtualDisk.md)

[Set-ResiliencySetting](./Set-ResiliencySetting.md)

