---
external help file: Msft_MiStreamTasks.cdxml-help.xml
Module Name: SoftwareInventoryLogging
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/softwareinventorylogging/publish-sildata?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-SilData
---

# Publish-SilData

## SYNOPSIS
Initiates a point in time collection of Software Inventory Logging data and forwards it, along with any accumulated historical data, to the aggregation server.
Windows Server 2012 R2 with KB3000850 applied.
For more information, see https://support.microsoft.com/kb/3000850.

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
The **Publish-SilData** cmdlet initiates a point in time collection of all Software Inventory Logging data, and forwards the data over the network to an aggregation server, if one is specified.
To identify the aggregation server, specify the **TargetUri** parameter of the Set-SilLogging cmdlet.
If Software Inventory Logging was started by an administrator by using the Start-SilLogging cmdlet, hourly collection and forwarding of data to the aggregation server commences.
In cases where Software Inventory Logging does not receive an acknowledgement from the aggregation server that data forwarding was successfully received, the feature stores that data locally and attempts to forward both cached and current data during the next scheduled forward attempt.
Once the cached and current data has been forwarded successfully, the feature deletes all historical data from the local server.

## EXAMPLES

### Example 1: Forward Software Inventory Logging data
```
PS C:\> Publish-SilData
```

This command initiates a point in time data collection of Software Inventory Logging data and forwards the data to an aggregation server.
To identify the aggregation server, specify the **TargetUri** parameter of the **Set-SilLogging** cmdlet.

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

### -CheckCollectionHistory
Indicates that this cmdlet checks whether the current data set varies from the previous collection results.
If it does vary, this cmdlet publishes a full set of the data to the aggregation server at the target uniform resource identifier (URI).
If the data set does not vary, this cmdlet publishes a small package of data that identifies the computer to the aggregation server.

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
Enter a computer name or a session object, such as the output of a New-CimSession https://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSession https://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
Specifies the name of a file.
This file is used by Software Inventory Logging to define the data sources.
Because Software Inventory Logging has an inherent default value, you do not usually need to specify this parameter.

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

### -UseCacheOnly
Indicates that the server can publish stored data to the aggregation server without triggering a point in time collection of all Software Inventory Logging data.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-SilData](./Get-SilData.md)

[Set-SilLogging](./Set-SilLogging.md)

[Start-SilLogging](./Start-SilLogging.md)

