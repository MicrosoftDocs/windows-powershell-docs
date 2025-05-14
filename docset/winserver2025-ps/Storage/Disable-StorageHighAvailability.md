---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Disk.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/disable-storagehighavailability?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-StorageHighAvailability
---

# Disable-StorageHighAvailability

## SYNOPSIS
Disables a Storage resource.

## SYNTAX

### ByDiskNumber (Default)
```
Disable-StorageHighAvailability [-DiskNumber] <UInt32[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [<CommonParameters>]
```

### ByDiskUniqueId
```
Disable-StorageHighAvailability -DiskUniqueId <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [<CommonParameters>]
```

### ByDiskName
```
Disable-StorageHighAvailability -DiskFriendlyName <String[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### ByDiskPath
```
Disable-StorageHighAvailability -DiskPath <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)
```
Disable-StorageHighAvailability -InputObject <CimInstance[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-StorageHighAvailability** cmdlet configures a Storage resource to be in an unavailable or inactive state.

## EXAMPLES

### Example 1: Disable a disk that is a resource in a failover cluster
```
This command uses the Get-Disk cmdlet to display the properties of disk number 9. The disk number is specific to the cluster node that owns the cluster disk resource.
PS C:\>Get-Disk -Number 9 | Format-Table -Property Number,IsHighlyAvailable,IsClustered,IsScaleOut

Number IsHighlyAvailable IsClustered IsScaleOut
------ ----------------- ----------- ----------
     9              True        True       True


The next command removes disk number 9 its failover cluster. The final command repeats the first command to display the new status of the disk.
PS C:\> Disable-StorageHighAvailability -DiskNumber 9
PS C:\> Get-Disk -Number 9 | Format-Table Number,IsHighlyAvailable,IsClustered,IsScaleOut

Number IsHighlyAvailable IsClustered IsScaleOut
------ ----------------- ----------- ----------
     9             False       False      False
```

This example removes a disk from a failover cluster by using its disk number.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -DiskFriendlyName
Specifies an array of friendly names of disks.

```yaml
Type: String[]
Parameter Sets: ByDiskName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskNumber
Specifies an array of disk numbers.

```yaml
Type: UInt32[]
Parameter Sets: ByDiskNumber
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskPath
Specifies an array of disk paths.

```yaml
Type: String[]
Parameter Sets: ByDiskPath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskUniqueId
Specifies an array of unique IDs, as strings, of disks.

```yaml
Type: String[]
Parameter Sets: ByDiskUniqueId
Aliases: DiskId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-Disk](./Get-Disk.md)

[Enable-StorageHighAvailability](./Enable-StorageHighAvailability.md)

