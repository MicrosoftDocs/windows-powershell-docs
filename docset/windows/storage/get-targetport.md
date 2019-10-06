---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: TargetPort.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-TargetPort
ms.reviewer:
ms.assetid: 4C139739-CDA3-4379-B87B-60B1B4DB8CD2
---

# Get-TargetPort

## SYNOPSIS
Returns a TargetPort object associated with a specific port address and connection type.

## SYNTAX

### ByName (Default)
```
Get-TargetPort [[-FriendlyName] <String[]>] [-ConnectionType <ConnectionType[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
Get-TargetPort [-UniqueId <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByAddress
```
Get-TargetPort [-PortAddress <String[]>] [-ConnectionType <ConnectionType[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageSubSystem
```
Get-TargetPort [-StorageSubSystem <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByMaskingSet
```
Get-TargetPort [-MaskingSet <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByTargetPortal
```
Get-TargetPort [-TargetPortal <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByVirtualDisk
```
Get-TargetPort [-VirtualDisk <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-TargetPort** cmdlet returns a TargetPort object associated with a specific port address and connection type.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> $StorageSubsystem = Get-StorageSubsystem
PS C:\> Get-Targetport -StorageSubsystem $StorageSubsystem
```

This example returns a list of target ports on the specified storage subsystem.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Parameter Sets: ByName, ByAddress
Aliases: 
Accepted values: Other, FibreChannel, ParallelSCSI, SSA, IEEE1394, RDMA, iSCSI, SAS, ADT

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
Parameter Sets: ByName
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaskingSet
Accepts a MaskingSet object as input.
The Masking Set CIM object is exposed by the [Get-MaskingSet](http://technet.microsoft.com/library/a7ef71fd-f7f6-4231-8799-0e96dd9eac84) cmdlet.

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

### -PortAddress
Specifies a string containing the port address to query.

```yaml
Type: String[]
Parameter Sets: ByAddress
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageSubSystem
Accepts a StorageSubsystem object as input.
The Storage Subsystem CIM object is exposed by the [Get-StorageSubsystem](http://technet.microsoft.com/library/ea364a0b-06d6-4653-b41c-be69b8038b54) cmdlet.

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

### -TargetPortal
Accepts a TargetPortal object as input.
The Target Portal CIM object is exposed by the Get-TargetPortal cmdlet.

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
Specifies an ID used to uniquely identify a Disk object in the system.
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

### -VirtualDisk
Accepts a VirtualDisk object as input.
The Virtual Disk CIM object is exposed by the [Get-VirtualDisk](http://technet.microsoft.com/library/0eeba53f-6468-485f-a680-49260b4c83f0) cmdlet.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

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

