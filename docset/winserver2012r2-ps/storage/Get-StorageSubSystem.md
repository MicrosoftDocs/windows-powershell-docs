---
external help file: StorageSubSystem.cdxml-help.xml
Module Name: Storage
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/storage/get-storagesubsystem?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StorageSubSystem
---

# Get-StorageSubSystem

## SYNOPSIS
Gets one or more StorageSubSystem objects.

## SYNTAX

### ByFriendlyName (Default)
```
Get-StorageSubSystem [[-FriendlyName] <String[]>] [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>]
 [-Model <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
Get-StorageSubSystem [-UniqueId <String[]>] [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>]
 [-Model <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByName
```
Get-StorageSubSystem [-Name <String[]>] [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>]
 [-Model <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByOffloadDataTransferSetting
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-OffloadDataTransferSetting <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByInitiatorId
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-InitiatorId <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByTargetPortal
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-TargetPortal <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByTargetPort
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-TargetPort <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByMaskingSet
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-MaskingSet <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByVirtualDisk
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-VirtualDisk <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByPhysicalDisk
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-PhysicalDisk <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStoragePool
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-StoragePool <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStorageNode
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-StorageNode <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStorageEnclosure
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-StorageEnclosure <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStorageProvider
```
Get-StorageSubSystem [-HealthStatus <HealthStatus[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-StorageProvider <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-StorageSubSystem** cmdlet gets one or more StorageSubSystem objects.
If no parameters are specified, then all subsystems on the system will be returned.
If two parameters are specified that conflict with unique values, then no subsystem will be returned; since none match that criteria.

## EXAMPLES

### Example 1: Get all storage subsystems
```
PS C:\>Get-StorageSubSystem
```

This example returns a list of all visible StorageSubSystem objects across all accessible StorageProvider objects.

### Example 2: Get the Storage Spaces subsystem
```
PS C:\>Get-StorageSubSystem -Model "Storage Spaces"
FriendlyName                            HealthStatus                            OperationalStatus
------------                            ------------                            -----------------
Storage Spaces on SRV1                  Healthy                                 OK
```

This example returns only the StorageSubSystem object for the Storage Spaces provider.

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
Parameter Sets: ByFriendlyName
Aliases: 

Required: False
Position: 0
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
Accepted values: Healthy, Warning, Unhealthy

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
Parameter Sets: ByInitiatorId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Manufacturer
Gets StorageSubSystem objects with the specified manufacturer name.

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

### -MaskingSet
Gets the StorageSubSystem for the specified MaskingSet object.
Enter a MaskingSet CIM object.
The MaskingSet object is exposed by the Get-MaskingSet cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByMaskingSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Model
Gets the StorageSubSystem with the specified model string.

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
Gets the StorageSubSystem with the specified name.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OffloadDataTransferSetting
Gets the StorageSubSystem associated with the specified OffloadDataTransferSetting object.
The Offload Data Transfer Setting CIM object is exposed by the Get-OffloadDataTransferSetting cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByOffloadDataTransferSetting
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PhysicalDisk
Gets the StorageSubSystem associated with the specified PhysicalDisk object.
The Physical Disk CIM object is exposed by the Get-PhysicalDisk cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByPhysicalDisk
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageEnclosure


```yaml
Type: CimInstance
Parameter Sets: ByStorageEnclosure
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageNode
Specifies a storage node as a **CimInstance** object.
The cmdlet gets storage subsystems on the node that you specify.
To obtain a storage node object, use the Get-StorageNode cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageNode
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StoragePool
Gets the StorageSubSystem associated with the specified StoragePool object.
The Storage Pool CIM object is exposed by the Get-StoragePool cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStoragePool
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageProvider
Gets the StorageSubSystem associated with the specified StorageProvider object.
The Storage Provider CIM object is exposed by the Get-StorageProvider cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageProvider
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetPort
Gets the StorageSubSystem associated with the specified TargetPort object.
The TargetPort CIM object is exposed by the Get-TargetPort cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByTargetPort
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetPortal
Gets the StorageSubSystem associated with the specified TargetPortal object.
The TargetPortal CIM object is exposed by the Get-TargetPortal cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByTargetPortal
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
Gets the StorageSubSystem with the specified UniqueID value.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualDisk
Gets the StorageSubSystem associated with the specified VirtualDisk object.
The Virtual Disk CIM object is exposed by the Get-VirtualDisk cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByVirtualDisk
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_InitiatorId
You can use the pipeline operator to pass an InitiatorID object to the **InitiatorID** parameter to get the storage subsystem associated with the object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
You can use the pipeline operator to pass a MaskingSet object to the **MaskingSet** parameter to get the storage subsystem associated with the object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_OffloadDataTransferSetting
You can use the pipeline operator to pass an OffloadDataTransferSetting object to the **OffloadDataTransferSetting** parameter to get the storage subsystem associated with the object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
You can use the pipeline operator to pass a PhysicalDisk object to the **PhysicalDisk** parameter to get the storage subsystem associated with the object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageNode
You can use the pipeline operator to pass a StorageNode object to the StorageNode parameter to get the storage subsystem associated with the object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
You can use the pipeline operator to pass a StoragePool object to the **StoragePool** parameter to get the storage subsystem associated with the object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageProvider
You can use the pipeline operator to pass a StorageProvider object to the **StorageProvider** parameter to get the storage subsystem associated with the object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_TargetPort
You can use the pipeline operator to pass a TargetPort object to the **TargetPort** parameter to get the storage subsystem associated with the object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_TargetPortal
You can the pipeline operator to pass a TargetPortal object to the TargetPortal parameter to get the storage subsystem associated with the object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can use the pipeline operator to pass a VirtualDisk object to the **VirtualDisk** parameter to get the storage subsystem associated with the object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubSystem
This cmdlet outputs an object representing a storage subsystem.

## NOTES

## RELATED LINKS

[Get-StorageProvider](./Get-StorageProvider.md)

[Set-StorageSubSystem](./Set-StorageSubSystem.md)

[Get-StorageNode](./Get-StorageNode.md)

