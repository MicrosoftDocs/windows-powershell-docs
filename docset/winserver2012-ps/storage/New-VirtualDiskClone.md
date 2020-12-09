---
external help file: Storage2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: C5ECB381-3631-4AB3-A0FD-DE20FC412E7B
manager: dansimp
---

# New-VirtualDiskClone

## SYNOPSIS
Creates a new clone of a specified virtual disk.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-VirtualDiskClone [-AsJob] [-CimSession <CimSession[]>] [-TargetStoragePoolName <String>]
 [-ThrottleLimit <Int32>] -FriendlyName <String> -InputObject <CimInstance[]>
```

### UNNAMED_PARAMETER_SET_2
```
New-VirtualDiskClone [-AsJob] [-CimSession <CimSession[]>] [-TargetStoragePoolName <String>]
 [-ThrottleLimit <Int32>] -FriendlyName <String> -VirtualDiskUniqueId <String[]>
```

### UNNAMED_PARAMETER_SET_3
```
New-VirtualDiskClone [-AsJob] [-CimSession <CimSession[]>] [-TargetStoragePoolName <String>]
 [-ThrottleLimit <Int32>] -FriendlyName <String> -VirtualDiskName <String[]>
```

### UNNAMED_PARAMETER_SET_4
```
New-VirtualDiskClone [-VirtualDiskFriendlyName] <String[]> [-AsJob] [-CimSession <CimSession[]>]
 [-TargetStoragePoolName <String>] [-ThrottleLimit <Int32>] -FriendlyName <String>
```

## DESCRIPTION
The **New-VirtualDiskClone** cmdlet creates a new clone of a specified virtual disk.

ps_storage_spacesubsystem_not_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>New-VirtualDiskClone -VirtualDiskFriendlyName "SQLData5" -TargetVirtualDiskName "SQLData5Clone" -TargetStoragePoolName "ClonePool"
```

This example creates a full clone of the specified Virtual Disk object.
Note: This cmdlet requires support from the Storage Management Provider.
This cmdlet returns the Virtual Disk object for the newly clone.

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
Specifies a friendly name for a virtual disk.
The friendly name may be defined by a user and is not guaranteed to be unique.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Accepts an object from the pipeline as input.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetStoragePoolName
Specifies the name of the target storage pool.
The name of the target storage pool that contains the virtual disk to be snapshot.

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

### -VirtualDiskFriendlyName
Specifies the friendly name of the virtual disk to be snapshot.
The friendly name may be defined by a user.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualDiskName
Specifies the name of the virtual disk.
This parameter is typically read-only.
This parameter is not equivalent to the **VirtualDiskFriendlyName** parameter that can be set by a user.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualDiskUniqueId
Specifies the unique ID of the virtual disk to be snapshot.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: VirtualDiskId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-VirtualDisk](./Get-VirtualDisk.md)

