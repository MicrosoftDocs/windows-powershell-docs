---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageEnclosure.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-storageenclosure?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StorageEnclosure
---

# Get-StorageEnclosure

## SYNOPSIS
Gets storage enclosures.

## SYNTAX

### ByUniqueId (Default)
```
Get-StorageEnclosure [-UniqueId <String[]>] [-Manufacturer <String[]>] [-Model <String[]>]
 [-HealthStatus <HealthStatus[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByFriendlyName
```
Get-StorageEnclosure [[-FriendlyName] <String[]>] [[-SerialNumber] <String[]>] [-Manufacturer <String[]>]
 [-Model <String[]>] [-HealthStatus <HealthStatus[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByPhysicalDisk
```
Get-StorageEnclosure [-Manufacturer <String[]>] [-Model <String[]>] [-HealthStatus <HealthStatus[]>]
 [-PhysicalDisk <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStorageNode
```
Get-StorageEnclosure [-Manufacturer <String[]>] [-Model <String[]>] [-HealthStatus <HealthStatus[]>]
 [-StorageNode <CimInstance>] [-PhysicallyConnected] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByStorageSubSystem
```
Get-StorageEnclosure [-Manufacturer <String[]>] [-Model <String[]>] [-HealthStatus <HealthStatus[]>]
 [-StorageSubSystem <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-StorageEnclosure** cmdlet gets storage enclosures that are visible to your computer.

## EXAMPLES

### Example 1: Get all enclosures
```
PS C:\>Get-StorageEnclosure
```

This command gets all the enclosures visible to your computer.

### Example 2: Get an enclosure by using a friendly name
```
PS C:\>Get-StorageEnclosure -FriendlyName "E1"
```

This command gets the enclosure named E1.

### Example 3: Get an enclosure by using an ID
```
PS C:\>Get-StorageEnclosure -UniqueId "{b2c21800-b833-11e2-9981-806e6f6e6963}"
```

This command gets the enclosure that has the specified **UniqueId**.

### Example 4: Get unhealthy enclosures
```
PS C:\>Get-StorageEnclosure -HealthStatus "Unhealthy"
```

This command gets enclosures that have the health status of Unhealthy.

### Example 5: Get enclosures from a manufacturer
```
PS C:\>Get-StorageEnclosure -Manufacturer "Fabrikam"
```

This command gets enclosures from a specific manufacturer.

### Example 6: Get an enclosure that contains a specified disk
```
PS C:\>Get-PhysicalDisk -FriendlyName "PhysicalDisk35" | Get-StorageEnclosure
```

This command uses the **Get-PhysicalDisk** cmdlet to get the disk named PhysicalDisk35, and then passes that object to the current cmdlet by using the pipeline operator.
The current cmdlet gets the enclosure that contains the disk named PhysicalDisk35.

### Example 7: Get enclosures attached to a storage node
```
PS C:\>Get-StorageNode -Name "Node14" | Get-StorageEnclosure
```

This command uses the **Get-StorageNode** cmdlet to get the storage node named Node14, and then passes that object to the current cmdlet by using the pipeline operator.
The current cmdlet gets enclosures attached to the node named Node14.

### Example 8: Get enclosures on a subsystem
```
PS C:\>Get-StorageSubSystem -FriendlyName "Clustered storage spaces on main cluster" | Get-StorageEnclosure
```

This command uses the **Get-StorageSubSystem** cmdlet to get the storage subsystem that has the specified friendly name, and then passes that object to the current cmdlet by using the pipeline operator.
The current cmdlet gets enclosures on the specified subsystem.

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

### -FriendlyName
Specifies an array of friendly names.
The cmdlet gets storage enclosures that the names specify.

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
Specifies an array of health status values.
The acceptable values for this parameter are:

- Healthy
- Warning
- Unhealthy
- Unknown

Health status describes the health of an enclosure.
This cmdlet gets the enclosures that have health statuses that this parameter specifies.

```yaml
Type: HealthStatus[]
Parameter Sets: (All)
Aliases:
Accepted values: Healthy, Warning, Unhealthy, Unknown

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Manufacturer
Specifies the name of a manufacturer.
This cmdlet gets enclosures for the manufacturers that this parameter identifies.

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
Specifies an array of model IDs.
This cmdlet gets enclosures that the model IDs specify.

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
Specifies a physical disk as a **CimInstance** object.
The cmdlet gets storage enclosures that contain the disk that the object specifies.
To obtain a physical disk object, use the Get-PhysicalDisk cmdlet.

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

### -PhysicallyConnected
Indicates that this cmdlet gets storage enclosures that are physically connected to a storage node.

```yaml
Type: SwitchParameter
Parameter Sets: ByStorageNode
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SerialNumber
Specifies the serial number of the storage enclosure to get.

```yaml
Type: String[]
Parameter Sets: ByFriendlyName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageNode
Specifies a storage node as a **CimInstance** object.
The cmdlet gets storage enclosures connected to the storage node that the object specifies.
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

### -StorageSubSystem
Specifies a storage subsystem as a **CimInstance** object.
This cmdlet gets storage enclosures that belong to the subsystem that the object specifies.
To obtain a storage subsystem object, use the Get-StorageSubSystem cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageSubSystem
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
Specifies an array of IDs.
This cmdlet gets the enclosures that the IDs specify.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### MSFT_StorageEnclosure[]
This cmdlet returns an array of **StorageEnclosure** objects.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-StorageEnclosureVendorData](./Get-StorageEnclosureVendorData.md)

[Disable-StorageEnclosureIdentification](./Disable-StorageEnclosureIdentification.md)

[Enable-StorageEnclosureIdentification](./Enable-StorageEnclosureIdentification.md)

[Get-PhysicalDisk](./Get-PhysicalDisk.md)

[Get-StorageNode](./Get-StorageNode.md)

[Get-StorageSubSystem](./Get-StorageSubsystem.md)

