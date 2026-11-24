---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Msft_MiStreamTasks.cdxml-help.xml
Module Name: SoftwareInventoryLogging
ms.date: 01/24/2017
online version: https://learn.microsoft.com/powershell/module/softwareinventorylogging/publish-sildata?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-SilData
---

# Publish-SilData

## SYNOPSIS
Initiates a point in time collection of all Software Inventory Logging data and forwards it, along with any accumulated historical data, to the aggregation server.

## SYNTAX

### CollectThenFlush (Default)
```
Publish-SilData [[-FileName] <String>] [-CheckCollectionHistory] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### FlushOnly
```
Publish-SilData [-UseCacheOnly] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Publish-SilData** cmdlet initiates a point in time collection of all Software Inventory Logging data, and forwards the data over the network to an aggregation server.
If Software Inventory Logging was started by an administrator, daily collection and forwarding of the data to the aggregation server commences.
In cases where Software Inventory Logging does not receive an acknowledgement from the aggregation server that data forwarding was successful, the service stores that data locally and attempts to forward both the previous and current data the next day.
Administrators can also use this cmdlet to manually forward all historical Software Inventory Logging data that was accumulated locally, if that data was not been successfully forwarded to the aggregation server for a period of one or more days.
After Software Inventory Logging successfully forwards the data, it deletes all historical data from the client server.

Use the Start-SilLogging cmdlet to start Software Inventory Logging.

Initiating Software Inventory Logging data collection uses server resources.
To reduce resource consumption, filter the data by using the *UseCacheOnly* parameter to specify that the cmdlet only forward the cached data and not initiate a point in time data collection.

Use the Set-SilLogging cmdlet with the *TargetUri* parameter to specify an aggregation server for daily collection.

## EXAMPLES

### Example 1: Forward Software Inventory Logging data
```
PS C:\> Publish-SilData
```

This command initiates a point in time data collection of Software Inventory Logging data and forwards the data to an aggregation server.

### Example 2: Publish existing stored data without first triggering a collection
```
PS C:\>Publish-SilData -UseCacheOnly
```

This command demonstrates the usage of *UseCacheOnly* mode.
The *UseCacheOnly* parameter indicates that the server can push or publish stored data to the aggregation server without triggering a point in time collection of all Software Inventory Logging data.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
 For more information about Windows PowerShellÂ® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -CheckCollectionHistory
Performs a comparison of the current data set to the last data set that was collected. If there are no differences, the contents of Get-SilComputerIdentity are sent.

```yaml
Type: SwitchParameter
Parameter Sets: CollectThenFlush
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

### -FileName
Specifies a file name.
This configuration file contains the data sources.

```yaml
Type: String
Parameter Sets: CollectThenFlush
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShellÂ® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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

### -UseCacheOnly
Indicates that the server can push or publish stored data to the aggregation server without triggering a point in time collection of all Software Inventory Logging data.

```yaml
Type: SwitchParameter
Parameter Sets: FlushOnly
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

### None

## NOTES

## RELATED LINKS

[Get-SilData](./Get-SilData.md)

