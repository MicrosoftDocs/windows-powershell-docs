---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-storagehealthaction?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StorageHealthAction
---

# Get-StorageHealthAction

## SYNOPSIS
Gets health-related system activities.

## SYNTAX

### ByUniqueId
```
Get-StorageHealthAction -UniqueId <String[]> [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### InputObject
```
Get-StorageHealthAction [-InputObject <CimInstance>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-StorageHealthAction** cmdlet gets health-related system activities for Storage subsystems, file shares, and volumes.

## EXAMPLES

### Example 1: Use the pipeline to get storage health actions
```
PS C:\>Get-StorageSubSystem -Model "Clustered Windows Storage" | Get-StorageHealthAction
```

This command gets the specified Storage subsystems, and uses the pipeline operator to pass them to **Get-StorageHealthAction**, which gets health-related activities for the subsytems.

### Example 2: Get the health actions for a volume
```
PS C:\>Get-StorageSubSystem -Model "Clustered Windows Storage" | Get-Volume | Get-StorageHealthAction
```

This command gets the specified Storage subsystem, and uses the pipeline operator to pass it to **Get-Volume**, which gets the volume, and then to **Get-StorageHealthAction**, which gets health-related activities for the volume.

### Example 3: Get the health actions for a file share
```
PS C:\>Get-StorageSubSystem -Model "Clustered Windows Storage" | Get-FileShare | Get-StorageHealthAction
```

This command gets the specified Storage subsystem, and uses the pipeline operator to pass it to **Get-FileShare**, which gets the file share, and then to **Get-StorageHealthAction**, which gets health-related activities for the file share.

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
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance
Parameter Sets: InputObject
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
Specifies an ID used to uniquely identify a Health Action object in the system.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_HealthAction

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

