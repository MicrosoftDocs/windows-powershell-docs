---
external help file: DnsServer_Cmdlets.xml
Module Name: DnsServer
online version: https://docs.microsoft.com/powershell/module/dnsserver/show-dnsservercache?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Show-DnsServerCache

## SYNOPSIS
Shows the records in a DNS Server Cache.

## SYNTAX

```
Show-DnsServerCache [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-ThrottleLimit <Int32>]
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Show-DNSServerCache** shows all cached Domain Name System (DNS) server resource records in the following format: Name, ResourceRecordData, Time-to-Live (TTL).

## EXAMPLES

### Example 1: Show all resource records in a DNS server cache
```
PS C:\> Show-DnsServerCache -ComputerName "Win12S-05.DNSServer-01.Contoso.com"
HostName                  RecordType Timestamp            TimeToLive      RecordData

--------                  ---------- ---------            ----------      ----------

@                         NS         0                    00:00:00        a.root-servers.net.

@                         NS         0                    00:00:00        b.root-servers.net.

@                         NS         0                    00:00:00        c.root-servers.net.

@                         NS         0                    00:00:00        d.root-servers.net.

@                         NS         0                    00:00:00        e.root-servers.net.

@                         NS         0                    00:00:00        f.root-servers.net.

@                         NS         0                    00:00:00        g.root- 

Win12S-05.DNSServer-01.... A          0                    00:46:48        172.23.90.136

localhost                 A          0                    17089.09:29:04  127.0.0.1

a.root-servers.net        A          0                    00:00:00        198.41.0.4

b.root-servers.net        A          0                    00:00:00
```

This command shows all resource records that exist in a specified DNS server cache.

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
The acceptable values for this parameter are: an IP V4 address; an IP V6 address; any other value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerResourceRecord[]

## NOTES

## RELATED LINKS

[Clear-DnsServerCache](./Clear-DnsServerCache.md)

[Get-DnsServerCache](./Get-DnsServerCache.md)

[Set-DnsServerCache](./Set-DnsServerCache.md)

