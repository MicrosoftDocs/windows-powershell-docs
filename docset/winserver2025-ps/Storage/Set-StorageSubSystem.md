---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageCmdlets.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/set-storagesubsystem?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-StorageSubSystem
---

# Set-StorageSubSystem

## SYNOPSIS
Modifies the properties of a StorageSubSystem object.

## SYNTAX

### ByUniqueIdDescription (Default)
```
Set-StorageSubSystem [-Description <String>] -UniqueId <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectSetAttributes
```
Set-StorageSubSystem [-InputObject] <CimInstance[]> [-AutomaticClusteringEnabled <Boolean>]
 [-FaultDomainAwarenessDefault <FaultDomainType>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByObjectDescription
```
Set-StorageSubSystem [-InputObject] <CimInstance[]> [-Description <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByNameDescription
```
Set-StorageSubSystem [-Description <String>] -Name <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFriendlyNameDescription
```
Set-StorageSubSystem [-Description <String>] [-FriendlyName] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueIdSetAttributes
```
Set-StorageSubSystem -UniqueId <String> [-AutomaticClusteringEnabled <Boolean>]
 [-FaultDomainAwarenessDefault <FaultDomainType>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByFriendlyNameSetAttributes
```
Set-StorageSubSystem [-FriendlyName] <String> [-AutomaticClusteringEnabled <Boolean>]
 [-FaultDomainAwarenessDefault <FaultDomainType>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByNameSetAttributes
```
Set-StorageSubSystem -Name <String> [-AutomaticClusteringEnabled <Boolean>]
 [-FaultDomainAwarenessDefault <FaultDomainType>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Set-StorageSubSystem** cmdlet modifies the properties of the specified StorageSubSystem object.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> $inpobject = (Get-StorageSubSystem)
PS C:\> Set-StorageSubSystem -InputObject $inpobject -Description "Non-Production Testing only"
```

This example changes the Description field on a StorageSubSystem object.

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

### -AutomaticClusteringEnabled
Indicates that storage pools and virtual disks are automatically added to the cluster.
By default, storage pools and virtual disks in a cluster are automatically added to the cluster.
If you want to disable this, set the value of this parameter to $False.

```yaml
Type: Boolean
Parameter Sets: ByObjectSetAttributes, ByUniqueIdSetAttributes, ByFriendlyNameSetAttributes, ByNameSetAttributes
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
Specifies a description of the object.
The description may be defined by a user.

```yaml
Type: String
Parameter Sets: ByUniqueIdDescription, ByObjectDescription, ByNameDescription, ByFriendlyNameDescription
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FaultDomainAwarenessDefault
Specifies the default fault domain for new virtual disks created with this storage subsystem.
The acceptable values for this parameter are:

- PhysicalDisk
- StorageScaleUnit
- StorageChassis
- StorageEnclosure
- StorageRack

The fault domain specifies at what level you want to be fault tolerant.
For example, specify StorageScaleUnit to store data copies on separate nodes of a Storage Spaces Direct cluster.
This cmdlet refers to nodes of a Storage Spaces Direct cluster as storage scale units because you can expand the scale of the cluster by adding more nodes.

```yaml
Type: FaultDomainType
Parameter Sets: ByObjectSetAttributes, ByUniqueIdSetAttributes, ByFriendlyNameSetAttributes, ByNameSetAttributes
Aliases:
Accepted values: PhysicalDisk, StorageEnclosure, StorageScaleUnit, StorageChassis, StorageRack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies the friendly name of the storage subsystem to modify.

```yaml
Type: String
Parameter Sets: ByFriendlyNameDescription, ByFriendlyNameSetAttributes
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
Parameter Sets: ByObjectSetAttributes, ByObjectDescription
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the storage subsystem to modify.

```yaml
Type: String
Parameter Sets: ByNameDescription, ByNameSetAttributes
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Specifies the ID of the storage subsystem to modify.

```yaml
Type: String
Parameter Sets: ByUniqueIdDescription, ByUniqueIdSetAttributes
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubSystem
You can use the pipeline operator to pass an array of MSFT_StorageSubsytem objects to the *InputObject* parameter.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-StorageSubSystem](./Get-StorageSubSystem.md)

