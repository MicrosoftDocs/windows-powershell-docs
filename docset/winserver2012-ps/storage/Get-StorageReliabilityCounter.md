---
external help file: Storage2_Cmdlets.xml
Module Name: Storage
online version: https://docs.microsoft.com/powershell/module/storage/get-storagereliabilitycounter?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-StorageReliabilityCounter

## SYNOPSIS
Gets the storage reliability counters for the disk or physical disk that you specify.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-StorageReliabilityCounter [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 -PhysicalDisk <CimInstance>
```

### UNNAMED_PARAMETER_SET_2
```
Get-StorageReliabilityCounter [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 -Disk <CimInstance>
```

## DESCRIPTION
Gets the storage reliability counters for the disk or physical disk that you specify.
These counters include information about such things as the device temperature, errors encountered, wear, and length of time the device has been in use.

## EXAMPLES

### Example 1: Get the counters for all physical disks
```
PS C:\>Get-PhysicalDisk | Get-StorageReliabilityCounter
```

This example pipes the output of the Get-PhysicalDisk cmdlet to the Get-StorageReliabilityCounter cmdlet, getting the counters for all physical disks.

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -Disk
Specifies the disk object for which to get storage reliability counters.
Enter a Disk CIM object.

Disk objects represent disks as seen by the operating system above the storage subsystem.
Disks could be actual physical hardware directly attached to the computer, or could be virtualized storage such as a virtual disk that has been assigned to a computer and appears to the operating system as a disk.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PhysicalDisk
Specifies the physical disk object for which to get storage reliability counters.
Enter a PhysicalDisk CIM object.

PhysicalDisk objects represent physical disks attached to a storage subsystem and located in a storage pool.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
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

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
You can pipe an MSFT_PhysicalDisk object to the PhysicalDisk parameter to get the storage reliability counters for the specified physical disk.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Disk
You can pipe an MSFT_Disk object to the Disk parameter to get the storage reliability counters for the specified disk.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageReliabilityCounter
The Get-StorageReliabilityCounter cmdlet returns a StorageReliabilityCounter object, or an array of StorageReliabilityCounter objects.

## NOTES

## RELATED LINKS

