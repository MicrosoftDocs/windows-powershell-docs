---
external help file: Storage2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 5314BD55-B77B-43F0-8680-DC3012F87440
manager: dansimp
---

# Update-StorageProviderCache

## SYNOPSIS
Updates the cache of the service for a particular provider and associated child objects.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Update-StorageProviderCache [[-Name] <String[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-DiscoveryLevel <DiscoveryLevel>] [-Manufacturer <String[]>] [-PassThru] [-RootObject <PSReference>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Update-StorageProviderCache [-AsJob] [-CimSession <CimSession[]>] [-DiscoveryLevel <DiscoveryLevel>]
 [-PassThru] [-RootObject <PSReference>] [-StorageSubSystem <CimInstance>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Update-StorageProviderCache [-AsJob] [-CimSession <CimSession[]>] [-DiscoveryLevel <DiscoveryLevel>]
 [-Manufacturer <String[]>] [-PassThru] [-RootObject <PSReference>] [-ThrottleLimit <Int32>] [-URI <Uri[]>]
```

### UNNAMED_PARAMETER_SET_4
```
Update-StorageProviderCache [-AsJob] [-CimSession <CimSession[]>] [-DiscoveryLevel <DiscoveryLevel>]
 [-PassThru] [-RootObject <PSReference>] [-ThrottleLimit <Int32>] [-UniqueId <String[]>]
```

### UNNAMED_PARAMETER_SET_5
```
Update-StorageProviderCache [-AsJob] [-CimSession <CimSession[]>] [-DiscoveryLevel <DiscoveryLevel>]
 [-PassThru] [-RootObject <PSReference>] [-ThrottleLimit <Int32>] -InputObject <CimInstance[]>
```

## DESCRIPTION
The **Update-StorageProviderCache** cmdlet updates the cache of the service for a particular provider and associated child objects.

Note: Using the Full value for the **DiscoveryLevel** parameter without using additional parameters to limit the scope to particular storage providers or storage subsystems causes all accessible storage providers to enumerate and report all state information, which can be extremely time intensive in large environments.

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

This example uses the **StorageSubsystem** parameter in association with the **Get-StorageSubSystem** cmdlet to get a particular storage subsystem and then perform a Level3 update on its associated storage provider, discovering all associated PhysicalDisk objects.

### Example 3: Update all objects for a specific storage pool
```
PS C:\>Update-StorageProviderCache -Name "StorageArray" -RootObject ([ref](Get-StoragePool "Storage pool"))
```

This example uses the **Name** parameter to specify the storage provider to update, and uses the **RootObject** parameter to specify the specific storage pool for which to update objects.
Because **RootObject** takes PSReference objects as input, you need to prepend the object call with `\[ref\]` to get a reference to the object instead of the object itself.

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

Required: False
Position: Named
Default value: Level0
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Accepts an MSFT_StorageProvider object from the pipeline as input.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Name
Specifies the name of the storage provider cache to update.

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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
You can pipe an MSFT_StorageSubsystem object to the **StorageSubsystem** parameter to perform the update on the storage provider for the specified subsystem.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageProvider
You can pipe an MSFT_StorageProvider object to the **InputObject** parameter to perform the update on the specified storage provider.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageProvider
By default the **Update-StorageProviderCache** cmdlet does not return any objects.
If you specify the **Passthru** parameter, this cmdlet returns an object representing the storage provider it updated.

## NOTES

## RELATED LINKS

[Get-StoragePool](./Get-StoragePool.md)

