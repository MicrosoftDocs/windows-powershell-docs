---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerForwarder_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/add-dnsserverforwarder?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DnsServerForwarder
---

# Add-DnsServerForwarder

## SYNOPSIS
Adds server level forwarders to a DNS server.

## SYNTAX

```
Add-DnsServerForwarder [-IPAddress] <IPAddress[]> [-ComputerName <String>] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DnsServerForwarder** cmdlet adds one or more forwarders to the forwarders list of a Domain Name System (DNS) server.
If you prefer one of the forwarders, put that forwarder first in the series of forwarder IP addresses.
After you first use this cmdlet to add forwarders to a DNS server, this cmdlet adds forwarders to the end of the forwarders list.

## EXAMPLES

### Example 1: Add a forwarder to a DNS server by using an IPv6 address
```
PS C:\> Add-DnsServerForwarder -IPAddress 2001:4898:7020:f100:458f:e6a2:fcaf:698c -PassThru
```

This command adds the IPv6 address 2001:4898:7020:f100:458f:e6a2:fcaf:698c to the list of forwarders on a local DNS server.

### Example 2: Add a forwarder to a DNS server by using an IP Address
```
PS C:\> Add-DnsServerForwarder -IPAddress 172.23.90.124 -PassThru
```

This command adds the IP address 172.23.90.124 to the list of forwarders on a local DNS server.

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
Specifies a remote DNS server.
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

### -IPAddress
Specifies an array of IP addresses of DNS servers where queries are forwarded.
If you prefer one of the forwarders, put that forwarder first in the series of forwarder IP addresses.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerForwarder

## NOTES

## RELATED LINKS

[Set-DnsServerForwarder](./Set-DnsServerForwarder.md)

[Remove-DnsServerForwarder](./Remove-DnsServerForwarder.md)

[Get-DnsServerForwarder](./Get-DnsServerForwarder.md)

[Add-DnsServerConditionalForwarderZone](./Add-DnsServerConditionalForwarderZone.md)

