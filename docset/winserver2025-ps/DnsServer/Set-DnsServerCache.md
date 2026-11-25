---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerCache_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/set-dnsservercache?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DnsServerCache
---

# Set-DnsServerCache

## SYNOPSIS
Modifies cache settings for a DNS server.

## SYNTAX

```
Set-DnsServerCache [-StoreEmptyAuthenticationResponse <Boolean>] [-MaxKBSize <UInt32>]
 [-PollutionProtection <Boolean>] [-ComputerName <String>] [-LockingPercent <UInt32>]
 [-MaxNegativeTtl <TimeSpan>] [-MaxTtl <TimeSpan>] [-PassThru] [-IgnorePolicies <Boolean>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsServerCache** cmdlet modifies cache settings for a Domain Name System (DNS) server.

## EXAMPLES

### Example 1: Set the maximum cache size on a DNS server
```
PS C:\> Set-DnsServerCache -MaxKBSize 10240 -ComputerName "Win12S-05.DNSServer-01.Contoso.com"
```

This command sets the maximum cache size to 10,240 KB on a DNS server that has an FQDN of Win12S-05.DNSServer-01.Contoso.com.

### Example 2: Set maximum Time-To-Live durations
```
PS C:\> Set-DnsServerCache -MaxTTL 02.00:00:00 -MaxNegativeTtl 00.00:20:00
```

This command sets the the maximum TTL to 2 days and the maximum negative TTL to 20 minutes.

## PARAMETERS

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
The acceptable values for this parameter are: an IPv4 address, an IPv6 address, and any other value that resolves to an IP address, such as fully qualified domain name (FQDN), host name, or NETBIOS name.

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

### -IgnorePolicies
Indicates whether to ignore policies for this cache.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LockingPercent
Specifies a percentage of the original Time to Live (TTL) value that caching can consume.

Cache locking is configured as a percent value.
For example, if the cache locking value is set to 50, the DNS server does not overwrite a cached entry for half of the duration of the TTL.
By default, the cache locking percent value is 100.
This value means that the DNS server will not overwrite cached entries for the entire duration of the TTL.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxKBSize
Specifies the maximum size, in kilobytes, of the memory cache of a DNS server.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxNegativeTtl
Specifies how long (1 to 2592000 seconds) an entry that records a negative answer to a query remains stored in the DNS cache. The value must be provided as a TimeSpan.
The default setting is 15 minutes.

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

### -MaxTtl
Specifies how long (0 to 2592000 seconds) a record is saved in cache. The value must be provided as a TimeSpan.
If the TimeSpan is set to 0 seconds, the DNS server does not cache records.
The default setting is one day (86,400 seconds).

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

### -PollutionProtection
Specifies whether DNS filters name service (NS) resource records that are cached.
Valid values are zero, which caches all responses to name queries and is the default value; and one, which caches only the records that belong to the same DNS subtree.

When you set this parameter value to False, cache pollution protection is disabled.
A DNS server caches the Host (A) record and all queried NS resources that are in the DNS server zone.
In this case, DNS can also cache the NS record of an unauthorized DNS server.
This event causes name resolution to fail or to be appropriated for subsequent queries in the specified domain.

When you set the value for this parameter to True, the DNS server enables cache pollution protection and ignores the Host (A) record.
The DNS server performs a cache update query to resolve the address of the NS if the NS is outside the zone of the DNS server.
The additional query minimally affects DNS server performance.

For more information about DNS cache locking, see [DNS Cache Locking](https://technet.microsoft.com/en-us/library/ee683892.aspx).
For more information about cache pollution protection, see [Securing the DNS Server Service](https://technet.microsoft.com/en-us/library/cc731367).
For more information about NS resource records, see [Managing resource records](https://technet.microsoft.com/en-us/library/cc783389.aspx).

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StoreEmptyAuthenticationResponse
Specifies whether a DNS server stores empty authoritative responses in the cache (RFC-2308).
The default value is True.

```yaml
Type: Boolean
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerCache

## NOTES

## RELATED LINKS

[RFC 2308](http://www.rfc-editor.org/rfc/rfc2308.txt)

[Clear-DnsServerCache](./Clear-DnsServerCache.md)

[Get-DnsServerCache](./Get-DnsServerCache.md)

[Show-DnsServerCache](./Show-DnsServerCache.md)

