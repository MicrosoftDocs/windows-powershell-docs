---
external help file: Storage2_Cmdlets.xml
Module Name: Storage
online version: https://docs.microsoft.com/powershell/module/storage/get-storagejob?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-StorageJob

## SYNOPSIS
Returns information about long-running Storage module jobs, such as a repair task.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-StorageJob [-AsJob] [-CimSession <CimSession[]>] [-JobState <JobState[]>] [-Name <String[]>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-StorageJob [-AsJob] [-CimSession <CimSession[]>] [-JobState <JobState[]>] [-Name <String[]>]
 [-StoragePool <CimInstance>] [-ThrottleLimit <Int32>] [-VirtualDisk <CimInstance>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-StorageJob [-AsJob] [-CimSession <CimSession[]>] [-JobState <JobState[]>] [-ThrottleLimit <Int32>]
 [-UniqueId <String[]>]
```

### UNNAMED_PARAMETER_SET_4
```
Get-StorageJob [-AsJob] [-CimSession <CimSession[]>] [-JobState <JobState[]>] [-StorageSubsystem <CimInstance>]
 [-ThrottleLimit <Int32>]
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

### -JobState
Gets storage jobs in the specified state.
Acceptable values are Completed, Exception, Killed, New, QueryPending, Running, Service, ShuttingDown, Starting, Suspended, and Terminated.

```yaml
Type: JobState[]
Parameter Sets: (All)
Aliases: 

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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_4
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
Specifies the ID of the storage job to retrieve.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

