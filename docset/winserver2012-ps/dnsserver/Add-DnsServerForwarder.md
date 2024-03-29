---
external help file: DnsServer_Cmdlets.xml
Module Name: DnsServer
online version: https://learn.microsoft.com/powershell/module/dnsserver/add-dnsserverforwarder?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-DnsServerForwarder

## SYNOPSIS
Adds server level forwarders to a DNS server.

## SYNTAX

```
Add-DnsServerForwarder [-IPAddress] <IPAddress[]> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-DnsServerForwarder** cmdlet adds one or more forwarders to a DNS server's forwarders list.
If you prefer one of the forwarders, put that forwarder first in the series of forwarder IP addresses.
After you first use this cmdlet to add forwarders to a DNS server, this cmdlet adds forwarders to the end of the forwarders list.

## EXAMPLES

### Example 1: Add a forwarder to a DNS server by using an IPv6 address
```
PS C:\> Add-DnsServerForwarder -IPAddress 2001:4898:7020:f100:458f:e6a2:fcaf:698c -PassThru
```

This command adds the IPv6 address 2001:4898:7020:f100:458f:e6a2:fcaf:698c to the list of forwarders on a local DNS server.

### Example 2: Add a forwarder to a DNS server by using an IPAddress
```
PS C:\>Add-DnsServerForwarder -IPAddress 172.23.90.124 -PassThru
```

This command adds the IP address 172.23.90.124 to the list of forwarders on a local DNS server.

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

### -IPAddress
Specifies an array of IP addresses of DNS servers where queries are forwarded.
If you prefer one of the forwarders, put that forwarder first in the series of forwarder IP addresses.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerForwarder

## NOTES

## RELATED LINKS

[Set-DnsServerForwarder](./Set-DnsServerForwarder.md)

[Remove-DnsServerForwarder](./Remove-DnsServerForwarder.md)

[Get-DnsServerForwarder](./Get-DnsServerForwarder.md)

[Add-DnsServerConditionalForwarderZone](./Add-DnsServerConditionalForwarderZone.md)

