---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerZoneAging_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/set-dnsserverzoneaging?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DnsServerZoneAging
---

# Set-DnsServerZoneAging

## SYNOPSIS
Configures DNS aging settings for a zone.

## SYNTAX

```
Set-DnsServerZoneAging [[-Aging] <Boolean>] [-Name] <String> [-ComputerName <String>]
 [-ScavengeServers <IPAddress[]>] [-RefreshInterval <TimeSpan>] [-NoRefreshInterval <TimeSpan>] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsServerZoneAging** cmdlet configures aging settings for a Domain Name System (DNS) server zone.

A resource record can remain on a DNS server after the resource is no longer part of the network.
Aging settings determine when a record can be removed, or scavenged, as a stale record.

## EXAMPLES

### Example 1: Set a scavenging server
```
PS C:\> Set-DnsServerZoneAging west01.contoso.com -Aging $True -ScavengeServers 172.18.1.1 -PassThru -Verbose
```

This command enables aging for a domain named west01.contoso.com and specifies a scavenging server.

## PARAMETERS

### -Aging
Indicates whether to enable aging and scavenging for a zone.
Aging and scavenging are not enabled by default.

For a value of $True, a DNS server refreshes time stamps for resource records when the server receives a dynamic update request.
This enables DNS servers to scavenge resource records.

For a value of $False, DNS servers do not refresh time stamps for resource records and do not scavenge resource records.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: AgingEnabled

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Specifies a DNS server.
If you do not specify this parameter, the command runs on the local system.
You can specify an IP address or any value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a zone.
This cmdlet is relevant only for primary zones.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ZoneName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoRefreshInterval
Specifies the length of time as a TimeSpan object.
This value is the interval between the last update of a timestamp for a record and the earliest time when the timestamp can be refreshed.
The minimum value is 0.
The maximum value is 8760 hours.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

If a resource record that has a non-zero time stamp is not refreshed for a period of the sum the values defined in the *NoRefreshInterval* parameter and the *RefreshInterval* parameter, a DNS server can remove that record during the next scavenging.

Do not select a value smaller than the longest refresh period of a resource record registered in the zone.

The minimum value is 0.
The maximum value is 8760 hours.
The default value is the same as the **DefaultRefreshInterval** property of the zone DNS server.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScavengeServers
Specifies an array of IP addresses for DNS servers.
These servers can scavenge records in this zone.
If you do not specify any scavenge servers, any primary DNS server that is authoritative for the zone can scavenge.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases:

Required: False
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerZoneAging

## NOTES

## RELATED LINKS

[Get-DnsServerZoneAging](./Get-DnsServerZoneAging.md)

