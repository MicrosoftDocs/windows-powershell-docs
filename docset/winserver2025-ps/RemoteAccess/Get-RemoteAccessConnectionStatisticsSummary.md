---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RemoteAccessConnectionStatisticsSummary_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-remoteaccessconnectionstatisticssummary?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RemoteAccessConnectionStatisticsSummary
---

# Get-RemoteAccessConnectionStatisticsSummary

## SYNOPSIS
Displays the summary statistics of real-time, currently active DirectAccess (DA) and VPN connections and the summary statistics of DA and VPN historical connections for a specified time duration.

## SYNTAX

### ActiveStatistics (Default)
```
Get-RemoteAccessConnectionStatisticsSummary [-ComputerName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### AccountingStatistics
```
Get-RemoteAccessConnectionStatisticsSummary [[-StartDateTime] <DateTime>] [[-EndDateTime] <DateTime>]
 [-ComputerName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RemoteAccessConnectionStatisticsSummary** cmdlet displays the summary statistics of real-time, currently active DirectAccess (DA) and VPN connections and the summary statistics of DA and VPN historical connections for a specified duration time.

The statistics summary for active and historical connections starting or ending on a Remote Access server are stored in the inbox accounting store on that server.
This cmdlet retrieves statistics summary for a specific server.
This cmdlet is not impacted by multi-site deployment.

 -- If neither a start date nor an end date is specified, then the statistics summary of active connections is retrieved.

 -- In order to retrieve statistics summary of historical data, a time duration needs to be specified such as a start date, an end date, or both.
If only one of them is specified, then the time stamp on the first or last record in the accounting database is used to fill the missing information and create a duration.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get- RemoteAccessConnectionStatisticsSummary -ComputerName edge1.corp.contoso.com
TotalConnections           : 0
TotalDAConnections         : 0

TotalVpnConnections        : 0

TotalUniqueUsers           : 0

MaxConcurrentConnections   : 10

TotalCumulativeConnections : 703

TotalBytesIn               : 1167785920

TotalBytesOut              : 3350338848

TotalBytesInOut            : 4518124768
```

This example gets the summary statistics for real-time, active connections.
There are no active users and hence the TotalConnections , TotalDAConnections, TotalVpnConnections and TotalUniqueUsers are `0`.

### EXAMPLE 2
```
PS C:\>$startdate = Get-Date -Date "12/25/2011"



PS C:\>$enddate = Get-Date -Date "01/10/2012"


When the start date or end date are specified, this cmdlet retrieves the counters from accounting store.
PS C:\>Get-RemoteAccessConnectionStatisticsSummary -StartDateTime $startdate -EndDateTime $enddate
TotalSessions         : 2314

TotalDASessions       : 2314

TotalVpnSessions      : 0

MaxConcurrentSessions : 28

TotalUniqueDAClients  : 27

AverageSessionsPerDay : 144

TotalUniqueUsers      : 57
```

This example gets the summary statistics for past connections.

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

### -ComputerName
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the remote access server computer specific tasks should be run.
When this parameter is specified the statistics summary on that Remote Access server is retrieved.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndDateTime
Specifies the time duration for which the statistics summary of historical connections is to be retrieved and indicates the end date.
If a date is not specified, then the time stamp of the last record in the accounting database is used by default.

```yaml
Type: DateTime
Parameter Sets: AccountingStatistics
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StartDateTime
Specifies the time duration for which the statistics summary of historical connections is to be retrieved and indicates the start date.
If a date is not specified, then the time stamp of the first record in the accounting database is used by default.

```yaml
Type: DateTime
Parameter Sets: AccountingStatistics
Aliases:

Required: False
Position: 1
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.DateTime

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#RemoteAccessConnectionSummary

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The RemoteAccessConnectionSummary object consists of the following properties:

For active connections:

 -- The total number of connections.

 -- The total number of DirectAccess connections.

 -- The total VPN number of connections.

 -- The total number of unique users.

 -- The maximum number of concurrent connections.

 -- The total number of cumulative connections (the total number of connections since the remote access server was started).

 -- The total number of bytes in.

 -- The total number of bytes out.

 -- The total number of bytes in and out.

## NOTES

## RELATED LINKS

[Get-RemoteAccessConnectionStatistics](./Get-RemoteAccessConnectionStatistics.md)

