---
external help file: StorageJob.cdxml-help.xml
Module Name: Storage
online version: 
schema: 2.0.0
title: Get-StorageJob
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 3A5CD3F6-C210-46C3-A46B-3B9BA113AF08
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-StorageJob

## SYNOPSIS
Returns information about long-running Storage module jobs, such as a repair task.

## SYNTAX

### ByFriendlyName (Default)
```
Get-StorageJob [<CommonParameters>]
```

### ByUniqueId
```
Get-StorageJob [-UniqueId <String[]>] [-JobState <JobState[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByVirtualDisk
```
Get-StorageJob [-Name <String[]>] [-JobState <JobState[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStoragePool
```
Get-StorageJob [-Name <String[]>] [-JobState <JobState[]>] [-StoragePool <CimInstance>]
 [-VirtualDisk <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### BySubsystem
```
Get-StorageJob [-JobState <JobState[]>] [-StorageSubsystem <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-StorageJob** cmdlet returns information about long-running Storage module jobs, such as a repair operation on a storage space.

## EXAMPLES

### Example 1: Get all current storage jobs
```
PS C:\>Get-StorageJob
Name                  ElapsedTime           JobState              PercentComplete       IsBackgroundTask
----                  -----------           --------              ---------------       ----------------
Regeneration          00:00:00              Running               50                    True
```

This example displays a list of all current storage jobs.

### Example 2: Get all storage jobs on the Storage Spaces subsystem
```
PS C:\>Get-StorageJob -StorageSubsystem (Get-StorageSubSystem -FriendlyName "Storage Spaces*")
```

This example gets all storage jobs on the Storage Spaces subsystem, using the Get-StorageSubSystem cmdlet to get the StorageSubsystem object.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

```yaml
Type: SwitchParameter
Parameter Sets: ByUniqueId, ByVirtualDisk, ByStoragePool, BySubsystem
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
Parameter Sets: ByUniqueId, ByVirtualDisk, ByStoragePool, BySubsystem
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobState
Gets storage jobs in the specified state.
Acceptable values are Completed, Exception, Killed, New, QueryPending, Running, Service, ShuttingDown, Starting, Suspended, and Terminated.

```yaml
Type: JobState[]
Parameter Sets: ByUniqueId, ByVirtualDisk, ByStoragePool, BySubsystem
Aliases: 
Accepted values: New, Starting, Running, Suspended, ShuttingDown, Completed, Terminated, Killed, Exception, Service, QueryPending

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name the storage job to get.

```yaml
Type: String[]
Parameter Sets: ByVirtualDisk, ByStoragePool
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePool
Specifies the storage pool object in which to retrieve storage jobs.
Enter a StoragePool CIM object.
The StoragePool CIM object is exposed by the Get-StoragePool cmdlet.

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

### -StorageSubsystem
Specifies the storage subsystem object in which to retrieve storage jobs.
Enter a StorageSubsystem CIM object.
The StorageSubsystem CIM object is exposed by the Get-StorageSubSystem cmdlet.

```yaml
Type: CimInstance
Parameter Sets: BySubsystem
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
Parameter Sets: ByUniqueId, ByVirtualDisk, ByStoragePool, BySubsystem
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UniqueId
Specifies the ID of the storage job to retrieve.

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
Specifies the virtual disk object for which to get storage jobs.
Enter a VirtualDisk CIM object.
The Virtual Disk CIM object is exposed by the Get-VirtualDisk cmdlet.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
You can pipe an MSFT_StoragePool object to the StoragePool parameter to specify the storage pool in which to get storage jobs.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
You can pipe an MSFT_StorageSubsystem object to the StorageSubsystem parameter to specify the storage subsystem for which to get storage jobs.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can pipe an MSFT_VirtualDisk object to the VirtualDisk parameter to specify the virtual disk for which to get storage jobs.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageJob
The Get-StorageJob cmdlet returns objects that represent storage jobs.

## NOTES

## RELATED LINKS

[Receive-Job](https://go.microsoft.com/fwlink/p/?LinkID=113372)

