---
external help file: DnsServer_Cmdlets.xml
Module Name: DnsServer
online version: https://learn.microsoft.com/powershell/module/dnsserver/set-dnsservercache?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DnsServerCache

## SYNOPSIS
Modifies cache settings for a DNS server.

## SYNTAX

```
Set-DnsServerCache [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-LockingPercent <UInt32>]
 [-MaxKBSize <UInt32>] [-MaxNegativeTtl <TimeSpan>] [-MaxTtl <TimeSpan>] [-PassThru]
 [-PollutionProtection <Boolean>] [-StoreEmptyAuthenticationResponse <Boolean>] [-ThrottleLimit <Int32>]
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-DnsServerCache** cmdlet modifies cache settings for a Domain Name System (DNS) server.

## EXAMPLES

### Example 1: Set the maximum cache size on a DNS server
```
PS C:\> Set-DnsServerCache -MaxKBSize 10240 -ComputerName "Win12S-05.DNSServer-01.Contoso.com"
```

This command sets the maximum cache size to 10,240 kilobytes on a DNS server that has an FQDN of Win12S-05.DNSServer-01.Contoso.com.

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
Specifies a DNS server.
The acceptable values for this parameter are: an IPv4 address, an IPv6 address, and any other value that resolves to an IP address, such as fully qualified domain name (FQDN), host name, or NETBIOS name.

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
Specifies how many seconds (0x1-0xFFFFFFFF) an entry that records a negative answer to a query remains stored in the DNS cache.
The default setting is 0x384 (900) seconds

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
Determines how many seconds (0x0-0xFFFFFFFF) a record is saved in cache.
If you use the 0x0 setting, the DNS server does not cache records.
The default setting is 0x15180 (86,400 seconds, or one day).

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
Determines whether DNS filters name service (NS) resource records that are cached.
Valid values are zero, which caches all responses to name queries and is the default value; and one, which caches only the records that belong to the same DNS subtree.

When you set this parameter value to False, cache pollution protection is disabled.
A DNS server caches the Host (A) record and all queried NS resources that are in the DNS server zone.
In this case, DNS can also cache the NS record of an unauthorized DNS server.
This event causes name resolution to fail or to be appropriated for subsequent queries in the specified domain.

When you set the value for this parameter to True, the DNS server enables cache pollution protection and ignores the Host (A) record.
The DNS server performs a cache update query to resolve the address of the NS if the NS is outside the zone of the DNS server.
The additional query minimally affects DNS server performance.

For more information about DNS cache locking, see DNS Cache Lockinghttp://technet.microsoft.com/en-us/library/ee683892(v=WS.10).aspx.
For more information about cache pollution protection, see Securing the DNS Server Servicehttp://technet.microsoft.com/en-us/library/cc731367.
For more information about NS resource records, see Managing resource recordshttp://technet.microsoft.com/en-us/library/cc783389(v=WS.10).aspx.

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
We recommend that you limit this value to either 0x00000000 or 0x00000001, but you can specify any value.
The default value is 0x00000001.
You must allow and treat literally the value zero.

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

### 
Class DNSServerCache

{

uint32 MaxCacheTTL; // Maximum time, in seconds, that the record of a recursive name query can remain in the DNS server cache.
The DNS server deletes records from the cache when the value of this entry expires, even if the value of the TTL field in the record is greater.
The default value of this property is 86,400 seconds (one day).

uint32  MaxNegativeCacheTTL; // Maximum time, in seconds, that a name error result from a recursive query can remain in the DNS server cache.
The DNS server deletes records from the cache when this timer expires, even if the TTL field is greater.
Default value is 86,400 (one day).

boolean AutoCacheUpdate // Indicates whether the DNS Server attempts to update its cache entries by using data from root servers.
When a DNS server starts, it needs a list of root server hints and Host A records for the server cache file.
Microsoft DNS servers have a feature that enables them to attempt to write back a new cache file based on the responses from root servers.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerCache

## NOTES

## RELATED LINKS

[RFC 2308](http://www.rfc-editor.org/rfc/rfc2308.txt)

[Clear-DnsServerCache](./Clear-DnsServerCache.md)

[Get-DnsServerCache](./Get-DnsServerCache.md)

[Show-DnsServerCache](./Show-DnsServerCache.md)

