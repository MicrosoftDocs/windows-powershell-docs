---
external help file: Storage2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: B5414111-13A8-44ED-8AF0-83F6A8192DB0
manager: dansimp
---

# New-VirtualDiskSnapshot

## SYNOPSIS
Creates a new snapshot of the specified virtual disk.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-VirtualDiskSnapshot [-AsJob] [-CimSession <CimSession[]>] [-TargetStoragePoolName <String>]
 [-ThrottleLimit <Int32>] -FriendlyName <String> -VirtualDiskUniqueId <String[]>
```

### UNNAMED_PARAMETER_SET_2
```
New-VirtualDiskSnapshot [-AsJob] [-CimSession <CimSession[]>] [-TargetStoragePoolName <String>]
 [-ThrottleLimit <Int32>] -FriendlyName <String> -InputObject <CimInstance[]>
```

### UNNAMED_PARAMETER_SET_3
```
New-VirtualDiskSnapshot [-AsJob] [-CimSession <CimSession[]>] [-TargetStoragePoolName <String>]
 [-ThrottleLimit <Int32>] -FriendlyName <String> -VirtualDiskName <String[]>
```

### UNNAMED_PARAMETER_SET_4
```
New-VirtualDiskSnapshot [-VirtualDiskFriendlyName] <String[]> [-AsJob] [-CimSession <CimSession[]>]
 [-TargetStoragePoolName <String>] [-ThrottleLimit <Int32>] -FriendlyName <String>
```

## DESCRIPTION
The **New-VirtualDiskSnapshot** cmdlet creates a new snapshot of the specified virtual disk.

ps_storage_spacesubsystem_not_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>New-VirtualDiskSnapshot -VirtualDiskFriendlyName "SQLData5" -TargetStoragePoolName "Snapshots"
```

This example creates a snapshot of the Virtual Disk object.
The cmdlet returns the resultant snapshot as a new Virtual Disk object.

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
Specifies a friendly name for a disk.
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetStoragePoolName
Specifies the name of the target storage pool.

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
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

