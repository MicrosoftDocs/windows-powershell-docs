---
external help file: Storage2_Cmdlets.xml
Module Name: Storage
online version: https://learn.microsoft.com/powershell/module/storage/update-hoststoragecache?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Update-HostStorageCache

## SYNOPSIS
Initiates an update on the host storage cache to reflect the current status of storage.

## SYNTAX

```
Update-HostStorageCache [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Update-HostStorageCache** cmdlet initiates an update on the host storage cache to reflect the current status of storage.
This is equivalent to a VDS Rescan, in that it will re-enumerate Disk, Partition, and Volume objects.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Update-HostStorageCache
```

This example updates the host-side storage cache.
This includes the Disk, Partition, and Volume objects and any child-items.
This cmdlet is equivalent to a VDS Rescan.

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

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Update-StorageProviderCache](./Update-StorageProviderCache.md)

