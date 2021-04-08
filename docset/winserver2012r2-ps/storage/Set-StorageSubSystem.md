---
author: Kateyanne
description: 
external help file: StorageCmdlets.cdxml-help.xml
manager: jasgro
Module Name: Storage
ms.author: v-kaunu
ms.date: 10/29/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/storage/set-storagesubsystem?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-StorageSubSystem
---

# Set-StorageSubSystem

## SYNOPSIS
Sets the friendly name or description of the specified StorageSubSystem object.

## SYNTAX

### ByUniqueIdDescription (Default)
```
Set-StorageSubSystem [-Description <String>] -UniqueId <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectClustering
```
Set-StorageSubSystem [-InputObject] <CimInstance[]> [-AutomaticClusteringEnabled <Boolean>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
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

### ByUniqueIdClustering
```
Set-StorageSubSystem -UniqueId <String> [-AutomaticClusteringEnabled <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFriendlyNameClustering
```
Set-StorageSubSystem [-FriendlyName] <String> [-AutomaticClusteringEnabled <Boolean>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByNameClustering
```
Set-StorageSubSystem -Name <String> [-AutomaticClusteringEnabled <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Set-StorageSubSystem** cmdlet sets the friendly name or description of the specified StorageSubSystem object.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> $inpobject = (Get-StorageSubSystem)
PS C:\> Set-StorageSubSystem -InputObject $inpobject -Description "Non-Production Testing only"
```

This example changes the Description field on a StorageSubSystem object.

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

### -AutomaticClusteringEnabled
Indicates whether the provider automatically clusters the spaces and pools in the clustered subsystem.
If you specify a value of $False for this parameter, you must manually add the pool or virtual disk to the cluster.

```yaml
Type: Boolean
Parameter Sets: ByObjectClustering, ByUniqueIdClustering, ByFriendlyNameClustering, ByNameClustering
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

### -FriendlyName
Specifies a friendly name for a disk.
The friendly name may be defined by a user and is not guaranteed to be unique.

```yaml
Type: String
Parameter Sets: ByFriendlyNameDescription, ByFriendlyNameClustering
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Accepts an object from the pipeline as input.

```yaml
Type: CimInstance[]
Parameter Sets: ByObjectClustering, ByObjectDescription
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
ps_storage_name_para

```yaml
Type: String
Parameter Sets: ByNameDescription, ByNameClustering
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
Specifies an ID used to uniquely identify a Disk object in the system.
The ID persists through restarts.

```yaml
Type: String
Parameter Sets: ByUniqueIdDescription, ByUniqueIdClustering
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubSystem
You can use the pipeline operator to pass an array of MSFT_StorageSubsytem objects to the **InputObject** parameter.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-StorageSubSystem](./Get-StorageSubSystem.md)

