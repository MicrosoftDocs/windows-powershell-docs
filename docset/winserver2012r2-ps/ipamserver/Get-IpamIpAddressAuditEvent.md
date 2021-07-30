---
external help file: IpamIpAuditEvent.cdxml-help.xml
Module Name: IpamServer
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/ipamserver/get-ipamipaddressauditevent?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IpamIpAddressAuditEvent
---

# Get-IpamIpAddressAuditEvent

## SYNOPSIS
Gets all IP address audit events in IPAM.

## SYNTAX

### ByUserName
```
Get-IpamIpAddressAuditEvent -UserName <String[]> -StartDate <DateTime> -EndDate <DateTime>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByIpAddress
```
Get-IpamIpAddressAuditEvent -IpAddress <String> -StartDate <DateTime> -EndDate <DateTime>
 [-CorrelateLogonEvents] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByClientId
```
Get-IpamIpAddressAuditEvent -ClientId <String> -StartDate <DateTime> -EndDate <DateTime>
 [-CorrelateLogonEvents] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByHostName
```
Get-IpamIpAddressAuditEvent -HostName <String> -StartDate <DateTime> -EndDate <DateTime>
 [-CorrelateLogonEvents] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamIpAddressAuditEvent** cmdlet gets all IP address audit events from an IP Address management (IPAM) server over a time interval.
IPAM enables IP address tracking through correlation of DHCP lease events on managed DHCP servers with user and machine authentication events on managed domain controllers and Network Policy Server (NPS) servers.
You can search correlated events by IP address, client ID, hostname, or username.
Use DHCP events between a start date and an end date to correlate data.
The data returned includes data for both the start date and the end date.

The cmdlet returns only the top 10,000 rows if the query results exceed more than 10,000 rows.
A warning occurs when this happens.
Narrow the search criteria to limit the results.

## EXAMPLES

### Example 1: Get all IP address audit events
```
PS C:\> $Today = Get-DatePS C:\>$LastMonth = $Today.AddDays(-30)PS C:\>$IpamIpAddressAuditEvents = Get-IpamIpAddressAuditEvent -StartDate $LastMonth -EndDate $Today
```

This command gets all IP address audit events between a start date and an end date.
The command gets only DHCP lease data.
The command stores the results in the variable named .**$IpamIpAddressAuditEvents**

### Example 2: Get all IP address audit events for an end date and a start date
```
PS C:\> $Today = Get-DatePS C:\>$LastMonth=$Today.AddDays(-30)PS C:\>$IpamIpAddressAuditEvents = Get-IpamIpAddressAuditEvent -StartDate $LastMonth -EndDate $Today -IpAddress 10.10.1.1
```

This command gets all IP address audit events for a given IP address, between a start date and an end date.
This command searches only DHCP lease events.
The command stores the results in the variable named **$IpamIpAddressAuditEvents**.

### Example 3: Get all IP address audit events, user events, and logon events for an end date and a start date
```
PS C:\> $Today = Get-DatePS C:\>$LastMonth=$today.AddDays(-30)PS C:\>$IpamIpAddressAuditEvents = Get-IpamIpAddressAuditEvent -StartDate $lastMonth -EndDate $today -IpAddress 10.10.1.1 -CorrelateLogonEvents
```

This command gets all IP address audit events for a given IP address, between a start date and an end date.
The command includes user and machine logon events from DC and NPS by using the **CorrelateLogonEvents** parameter.
The command stores the results in the variable named **$IpamIpAddressAuditEvents**.

### Example 4: Get all IP address audit events by MAC address
```
PS C:\> $Today = Get-DatePS C:\>$LastMonth=$Today.AddDays(-30)PS C:\>$IpamIpAddressAuditEvents = Get-IpamIpAddressAuditEvent -StartDate $LastMonth -EndDate $Today -ClientId "AA:BB:CC:DD:EE:FF" -CorrelateLogonEvents
```

This command gets all IP address audit events for a client ID, between a start date and an end date.
The command includes user and machine log-on events from DC and NPS by using the **CorrelateLogonEvents** parameter.
The command stores the results in the variable named **$IpamIpAddressAuditEvents**.

### Example 5: Get all IP address audit events by hostname
```
PS C:\> $Today = Get-DatePS C:\>$LastMonth=$Today.AddDays(-30)PS C:\>$IpamIpAddressAuditEvents = Get-IpamIpAddressAuditEvent -StartDate $LastMonth -EndDate $Today -HostName client1.contoso.com -CorrelateLogonEvents
```

This command gets all IP address audit events for a given hostname, between a start date and an end date.
Also include user and machine log-on events from DC and NPS by using -CorrelateLogonEvents option.
The command stores the results in the variable named **$IpamIpAddressAuditEvents**.

### Example 6: Get all IP address audit events by username
```
PS C:\> $Today = Get-DatePS C:\>$LastMonth=$Today.AddDays(-30)PS C:\>$IpamIpAddressAuditEvents = Get-IpamIpAddressAuditEvent -StartDate $LastMonth -EndDate $Today -HostName client1.contoso.com
```

This command gets all IP address audit events for a username, between a start date and an end date.
Since username is available only from authentication data, this data is always included while querying for audit events based on username.
The command stores the results in the variable named **$IpamIpAddressAuditEvents**.

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

### -ClientId
Specifies an array of client IDs.
Use this parameter to search for audit events by MAC address.
You may use dashes (-) in the client ID but they are not required.

```yaml
Type: String
Parameter Sets: ByClientId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CorrelateLogonEvents
Indicates that the cmdlet correlates logon events.
Use this parameter to include or exclude user and machine events from domain controllers and NPS servers.
If you specify this parameter, logon events are included in the correlated set of events retrieved by this cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: ByIpAddress, ByClientId, ByHostName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndDate
Specifies the end date, as a DateTime object, for which to get the event data.
To get a DateTime object, use the **Get-Date** cmdlet and specify the date in **DD/MM/YYYY** format.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HostName
Specifies an array of host names.
Use this parameter to search correlated events by host name.

```yaml
Type: String
Parameter Sets: ByHostName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IpAddress
Specifies an IP address.
Use this parameter to search correlated events by IPv4 address.
The cmdlet does not support IPv6 address tracking.

```yaml
Type: String
Parameter Sets: ByIpAddress
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartDate
Specifies the start date as a DateTime object.
To get a DateTime object, use the **Get-Date** cmdlet and specify the date in **DD/MM/YYYY** format.

```yaml
Type: DateTime
Parameter Sets: (All)
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

### -UserName
Specifies an array of user names.
Use this parameter to search correlated events by username.
Searching by user's domain name is not supported.
Logon events are included in this search because user names are not specified in DHCP lease events.

```yaml
Type: String[]
Parameter Sets: ByUserName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### IpamIpAuditEvent
Represents an IP address audit event in IPAM

## NOTES

## RELATED LINKS

[Remove-IpamIpAddressAuditEvent](./Remove-IpamIpAddressAuditEvent.md)

