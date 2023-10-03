---
external help file: DnsServer_Cmdlets.xml
Module Name: DnsServer
online version: https://learn.microsoft.com/powershell/module/dnsserver/set-dnsserverscavenging?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DnsServerScavenging

## SYNOPSIS
Changes DNS server scavenging settings.

## SYNTAX

```
Set-DnsServerScavenging [[-ScavengingState] <Boolean>] [[-RefreshInterval] <TimeSpan>]
 [[-NoRefreshInterval] <TimeSpan>] [[-ScavengingInterval] <TimeSpan>] [-ApplyOnAllZones] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Set-DnsServerScavenging** cmdlet changes scavenging settings on a DNS server.
If any of the set operations fail, the cmdlet continues to configure other settings.
The cmdlet displays the settings that it changed and the settings that it did not change.

## EXAMPLES

### Example 1: Change the refresh interval for a resource record
```
PS C:\> Set-DnsServerScavenging -RefreshInterval 1.00:00:00 -Verbose -PassThru
```

This command changes the refresh interval to 1 day for scavenging on a local DNS server.

## PARAMETERS

### -ApplyOnAllZones
Applies the server settings on all zones.

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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies a remote DNS server.
You can specify an IP address or any value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoRefreshInterval
Specifies a length of time as a TimeSpan object.
**NoRefreshInterval** sets a period of time in which no refreshes are accepted for dynamically updated records.
Zones on the server inherit this value automatically.

This value is the interval between the last update of a timestamp for a record and the earliest time when the timestamp can be refreshed.
The minimum value is 0.
The maximum value is 8760 hours (seven days).

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -RefreshInterval
Specifies the refresh interval as a TimeSpan object.
During this interval, a DNS server can refresh a resource record that has a non-zero time stamp.
Zones on the server inherit this value automatically.

If a DNS server does not refresh a resource record that has a non-zero time stamp, the DNS server can remove that record during the next scavenging.

Do not select a value smaller than the longest refresh period of a resource record registered in the zone.

The minimum value is 0.
The maximum value is 8760 hours (seven days).
The default value is the same as the **DefaultRefreshInterval** property of the zone DNS server.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScavengingInterval
Specifies a length of time as a TimeSpan object.
**ScavengingInterval** determines whether the scavenging feature for the DNS server is enabled and sets the number of hours between scavenging cycles.

The default setting is 0, which disables scavenging for the DNS server.
A setting greater than 0 enables scavenging for the server and sets the number of hours between scavenging cycles.
The minimum value is 0.
The maximum value is 8760 hours (seven days).

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScavengingState
Enables or disables automatic scavenging of stale records.
**ScavengingState** determines whether the DNS scavenging feature is enabled by default on newly created zones.
The acceptable values for this parameter are:
- $False.
Disables scavenging.
This is the default setting.
- $True.
Enables scavenging

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerScavenging

## NOTES

## RELATED LINKS

[Get-DnsServerScavenging](./Get-DnsServerScavenging.md)

[Start-DnsServerScavenging](./Start-DnsServerScavenging.md)

