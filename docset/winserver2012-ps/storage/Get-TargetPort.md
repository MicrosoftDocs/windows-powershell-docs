---
author: Kateyanne
external help file: Storage2_Cmdlets.xml
manager: dansimp
Module Name: Storage
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/storage/get-targetport?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-TargetPort

## SYNOPSIS
Returns a TargetPort object associated with a specific port address and connection type.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-TargetPort [[-FriendlyName] <String[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-ConnectionType <ConnectionType[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-TargetPort [-AsJob] [-CimSession <CimSession[]>] [-TargetPortal <CimInstance>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-TargetPort [-AsJob] [-CimSession <CimSession[]>] [-StorageSubSystem <CimInstance>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_4
```
Get-TargetPort [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-VirtualDisk <CimInstance>]
```

### UNNAMED_PARAMETER_SET_5
```
Get-TargetPort [-AsJob] [-CimSession <CimSession[]>] [-MaskingSet <CimInstance>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_6
```
Get-TargetPort [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-UniqueId <String[]>]
```

### UNNAMED_PARAMETER_SET_7
```
Get-TargetPort [-AsJob] [-CimSession <CimSession[]>] [-ConnectionType <ConnectionType[]>]
 [-PortAddress <String[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-TargetPort** cmdlet returns a TargetPort object associated with a specific port address and connection type.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>$StorageSubsystem = Get-StorageSubsystem



PS C:\>Get-Targetport -StorageSubsystem $StorageSubsystem
```

This example returns a list of target ports on the specified storage subsystem.

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

### -ConnectionType
Specifies the type of the connection.
The acceptable values for this parameter are:iSCSI, SAS, Fibre Channel, and so on.

```yaml
Type: ConnectionType[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_7
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FriendlyName
Specifies a friendly name for a disk.
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

### -MaskingSet
Accepts a MaskingSet object as input.
The Masking Set CIM object is exposed by the Get-MaskingSethttp://technet.microsoft.com/library/a7ef71fd-f7f6-4231-8799-0e96dd9eac84 cmdlet.

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

### -PortAddress
Specifies a string containing the port address to query.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_7
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -TargetPortal
Accepts a TargetPortal object as input.
The Target Portal CIM object is exposed by the Get-TargetPortal cmdlet.

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

### -VirtualDisk
Accepts a VirtualDisk object as input.
The Virtual Disk CIM object is exposed by the Get-VirtualDiskhttp://technet.microsoft.com/library/0eeba53f-6468-485f-a680-49260b4c83f0 cmdlet.

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

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_TargetPortal
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_TargetPort
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-StorageSubsystem](./Get-StorageSubsystem.md)

