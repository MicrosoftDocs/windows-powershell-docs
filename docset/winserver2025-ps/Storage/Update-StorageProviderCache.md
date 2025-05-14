---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageProvider.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/update-storageprovidercache?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-StorageProviderCache
---

# Update-StorageProviderCache

## SYNOPSIS
Updates the cache of the service for a particular provider and associated child objects.

## SYNTAX

### ByName (Default)
```
Update-StorageProviderCache [[-Name] <String[]>] [-Manufacturer <String[]>] [-DiscoveryLevel <DiscoveryLevel>]
 [-RootObject <PSReference>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [<CommonParameters>]
```

### ByUniqueId
```
Update-StorageProviderCache [-UniqueId <String[]>] [-DiscoveryLevel <DiscoveryLevel>]
 [-RootObject <PSReference>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [<CommonParameters>]
```

### ByURI
```
Update-StorageProviderCache [-Manufacturer <String[]>] [-URI <Uri[]>] [-DiscoveryLevel <DiscoveryLevel>]
 [-RootObject <PSReference>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [<CommonParameters>]
```

### ByStorageSubSystem
```
Update-StorageProviderCache [-StorageSubSystem <CimInstance>] [-DiscoveryLevel <DiscoveryLevel>]
 [-RootObject <PSReference>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Update-StorageProviderCache -InputObject <CimInstance[]> [-DiscoveryLevel <DiscoveryLevel>]
 [-RootObject <PSReference>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [<CommonParameters>]
```

## DESCRIPTION
The **Update-StorageProviderCache** cmdlet updates the cache of the service for a particular provider and associated child objects.

Note: Using the Full value for the *DiscoveryLevel* parameter without using additional parameters to limit the scope to particular storage providers or storage subsystems causes all accessible storage providers to enumerate and report all state information, which can be extremely time intensive in large environments.

## EXAMPLES

### Example 1: Perform a Full update of all objects
```
PS C:\>Update-StorageProviderCache -DiscoveryLevel Full
```

This example performs a Full update of the storage provider cache on all accessible storage providers, rescanning all associated physical disks and reporting the state.
This operation can be extremely time intensive in large or enterprise environments; instead use parameters to scope the update.

### Example 2: Update PhysicalDisk objects for a particular storage provider
```
PS C:\>Update-StorageProviderCache -StorageSubSystem (Get-StorageSubSystem -FriendlyName "StorageArray*") -DiscoveryLevel Level3
```

This example uses the *StorageSubsystem* parameter in association with the **Get-StorageSubSystem** cmdlet to get a particular storage subsystem and then perform a Level3 update on its associated storage provider, discovering all associated PhysicalDisk objects.

### Example 3: Update all objects for a specific storage pool
```
PS C:\>Update-StorageProviderCache -Name "StorageArray" -RootObject ([ref](Get-StoragePool "Storage pool"))
```

This example uses the *Name* parameter to specify the storage provider to update, and uses the *RootObject* parameter to specify the specific storage pool for which to update objects.
Because *RootObject* takes PSReference objects as input, you need to prepend the object call with `\[ref\]` to get a reference to the object instead of the object itself.

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

### -DiscoveryLevel
Defines the level (or depth) of discovery that should be performed.
Increasing levels are cumulative; the storage providers will discover objects starting from Level0 and continuing to the highest level specified.
Acceptable values are:

Full, which discovers all objects on all accessible storage providers.
This is the same as a Level3 discovery.

Level0, which discovers storage provider and storage subsystem objects.

Level1, which performs a Level0 discovery and then discovers storage pools, resiliency settings, target ports, target portals, and initiator identifiers.

Level2, which performs a Level1 discovery and then discovers virtual disk and masking set objects.

Level3, which performs a Level2 discovery and then discovers physical disk objects.
This is the same as a Full discovery.

All storage providers perform a Level0 or higher level discovery when loaded by Windows.

```yaml
Type: DiscoveryLevel
Parameter Sets: (All)
Aliases:
Accepted values: Level0, Level1, Level2, Level3, Full

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

### -Manufacturer
Specifies the storage provider cache to update by manufacturer name.
Enter a manufacturer string, or use wildcard characters to enter a pattern.

```yaml
Type: String[]
Parameter Sets: ByName, ByURI
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the storage provider cache to update.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Specifies that the cmdlet should output an object representing the storage provider it updated.
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

### -RootObject
Specifies a reference to the object from which you want to begin discovering associated objects.
When the DiscoveryLevel parameter is not specified, well-defined actions will be taken depending on the type of object reference specified:

StorageSubsystem: All associated objects will be discovered.

StoragePool: The pool, along with any associated resiliency settings, virtual disks, and physical disks will be discovered.

MaskingSet: The masking set, along with any associated target ports, initiator identifiers, and virtual disks will be discovered.

For all other objects, only the specified object will be discovered or refreshed.

```yaml
Type: PSReference
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageSubSystem
Updates all storage subsystems managed by the storage provider associated with the StorageSubsystem object you specify.
Enter a StorageSubsytem CIM object, which is exposed by the Get-StorageSubSystem cmdlet.

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

### -URI
Specifies the URI of the storage provider whose cache should be updated.

```yaml
Type: Uri[]
Parameter Sets: ByURI
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UniqueId
Specifies the ID of the storage provider cache to update.
Type one or more IDs, with each ID enclosed in quotes, and multiple IDs separated by commas.
The ID persists through restarts.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
You can pipe an MSFT_StorageSubsystem object to the *StorageSubsystem* parameter to perform the update on the storage provider for the specified subsystem.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageProvider
You can pipe an MSFT_StorageProvider object to the *InputObject* parameter to perform the update on the specified storage provider.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageProvider
By default the **Update-StorageProviderCache** cmdlet does not return any objects.
If you specify the *PassThru* parameter, this cmdlet returns an object representing the storage provider it updated.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-StoragePool](./Get-StoragePool.md)

