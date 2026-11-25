---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RemoteAccessConnectionStatistics_v2.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-remoteaccessconnectionstatistics?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RemoteAccessConnectionStatistics
---

# Get-RemoteAccessConnectionStatistics

## SYNOPSIS
Displays the statistics of real-time, currently active DirectAccess (DA) and VPN connections and the statistics of DA and VPN historical connections for a specified time duration.

## SYNTAX

### ActiveStatistics (Default)
```
Get-RemoteAccessConnectionStatistics [-ComputerName <String>] [-ResourceName <String>]
 [-RoutingDomain <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### AccountingStatistics
```
Get-RemoteAccessConnectionStatistics [-ComputerName <String>] [[-StartDateTime] <DateTime>]
 [[-EndDateTime] <DateTime>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-RemoteAccessConnectionStatistics** cmdlet displays the statistics of the real-time, currently active DirectAccess (DA) and VPN connections and the statistics of DA and VPN historical connections for a specified time duration.

The statistics for active and historical connections starting or ending on a Remote Access (RA) server are stored in the inbox accounting store on that server.
This cmdlet retrieves statistics for a specific server.
This cmdlet is not impacted by multi-site deployment.

 -- If neither a start date nor an end date is specified, then statistics for active connections is retrieved.

 -- In order to retrieve statistics of historical data, a time duration needs to be specified such as a start date, an end date, or both.
If only one of them is specified then the time stamp on the first or last record in the accounting database is used to fill the missing information and to create a duration time.

The statistics of active connections can be explicitly filtered by the resource accessed over the connections or by the security group that users who originated the connections belong to.
These filters are not available for statistics of historical connections.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-RemoteAccessConnectionStatistics | Format-List -Property *
ClientIPAddress       : {10.1.1.11, 2002:836b:2:2000:7407:f734:9281:f9a3}
UserName              : {corp.contoso.com \remoteuser1}
ConnectionDuration(s) : 220
ConnectionType        : Vpn
AccessStatus          : User Mode/Full Corp Access

PS C:\>Disconnect-VpnUser -HostIPAddress 10.1.1.11 -PassThru10.1.1.11

PS C:\>Get-RemoteAccessConnectionStatistics | Format-List -Property *
```

This example disconnects the connection by specifying the IP address of the host from which it originates.
The output of the disconnect cmdlet displays the IP address of the disconnected host.
For this example there is one active VPN connection.
The output of this cmdlet is piped to the [Format-List](https://go.microsoft.com/fwlink/p/?LinkId=113302) cmdlet to display the details of the active connection in a list format.

### EXAMPLE 2
```
PS C:\>$startDate = Get-Date -Date "12/23/2011"

PS C:\>$endDate = Get-Date -Date "05/23/2012"

PS C:\>Get-RemoteAccessConnectionStatistics -StartDateTime $startDate -EndDateTime $endDate | Export-Csv -Path "data.csv"
```

This example gets a list of historic connections and export them to a .csv file.

### EXAMPLE 3
```
PS C:\>$enddate = Get-Date -Date "12/23/2011"

The data is exported from server start date to the specified end date. Note: The starting date does not need to be explicitly specified here.
PS C:\>Get-RemoteAccessConnectionStatistics -EndDateTime $enddate | Export-Csv -Path "data.csv"
```

This example exports a list of historic connections up to a specific date.

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
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the RA server computer specific tasks should be run.
When this parameter is specified, the statistics on the RA server are retrieved.

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
Specifies the time duration for which the statistics of historical connections is to be retrieved and indicates the end date.
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

### -ResourceName
Enables a user to filter the statistics of active connections based on the server, or resource, that the end-user is accessing.
This parameter indicates the IP address or host name of the server, or resource, that a user is accessing.

```yaml
Type: String
Parameter Sets: ActiveStatistics
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RoutingDomain
Specifies the name of the routing domain.

```yaml
Type: String
Parameter Sets: ActiveStatistics
Aliases: RoutingDomainName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartDateTime
Specifies the time duration for which the statistics of historical connections is to be retrieved and indicates the start date.
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

### System.String

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

### Microsoft.Management.Infrastructure.CimInstance#RemoteAccessConnection

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

For real-time statistics, the array of RemoteAccessConnection objects consists of the following properties.
A separate instance of the object is output for every connection.

 -- The user name of the user logged in.

 -- The state of user activity on the connection, idle or active.

 -- The bandwidth used by the connection.

 -- The IPv4 address of the client computer.

 -- The IPv6 address of the client computer.

 -- The host name of the client computer.

 -- The internet-facing IP address of the client.

 -- The tunnel type: VPN tunnel or ESP tunnel for DA.

 -- The transition technology used in the DA connection: native IPv6, Teredo, IPHTTPS, Isatap, 6to4.

 -- The time stamp when the connection was setup.

 -- The time duration of connection.

 -- The total number of bytes received on the connection so far.

 -- The total number of bytes sent on the connection so far.

 -- The connection type: DA or VPN.

 -- The health status: Indicates the NAP health status.

 -- The authentication method used to authenticate the user and computer in VPN and DA.

For accounting statistics, the array of RemoteAccessConnection objects consists of the following properties.
A separate instance of the object is outputted for every connection.
- The user name of the user logged in.

- The IPv4 address of the client computer.

 -- The IPv6 address of the client computer.

 -- The host name of the client computer.

 -- The internet-facing IP address of the client.

 -- The tunnel type: VPN tunnel or ESP tunnel for DA.

- The transition technology used in the DA connection: native IPv6, Teredo, IPHTTPS, Isatap, 6to4.

 -- The time stamp when the connection was setup.

 -- The time duration of connection.

 -- The total number of bytes received on the connection so far.

 -- The total number of bytes sent on the connection so far.

 -- The connection type: DA or VPN.

 -- The health status: Indicates the NAP health status.

 -- The authentication method used to authenticate the user and computer in VPN and DA.

## NOTES

## RELATED LINKS

[Export-Csv](https://go.microsoft.com/fwlink/p/?LinkId=113299)

[Format-List](https://go.microsoft.com/fwlink/p/?LinkId=113302)

[Get-Date](https://go.microsoft.com/fwlink/p/?LinkId=113313)

[Get-RemoteAccessConnectionStatisticsSummary](./Get-RemoteAccessConnectionStatisticsSummary.md)

