---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServer_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/test-dnsserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-DnsServer
---

# Test-DnsServer

## SYNOPSIS
Tests that a specified computer is a functioning DNS server.

## SYNTAX

### Context (Default)
```yaml
Test-DnsServer [-IPAddress] <IPAddress[]> [-ComputerName <String>] [[-Context] <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ZoneMaster
```yaml
Test-DnsServer [-IPAddress] <IPAddress[]> [-ComputerName <String>] -ZoneName <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Test-DnsServer cmdlet** tests whether a computer is a functioning Domain Name System (DNS) server.
The DNS server must be running Windows Server® 2008 R2 operating system or above.

When you specify a computer by its IP address only, the cmdlet tests whether the computer is a DNS server.
If you also specify a zone name, the cmdlet validates that the DNS server can resolve the specified zone.

## EXAMPLES

### Example 1: Test whether a DNS server is functional
```Powershell
PS C:\> Test-DnsServer -IPAddress 10.123.183.155

IPAddress               Result                  RoundTripTime           TcpTried                UdpTried
---------               --------                 ------------           --------                --------
10.123.183.155           Success                 00:00:11                False                  True
```

This command tests whether the computer that has an IP address of 10.123.183.155 is a functional DNS server.

### Example 2: Test whether a DNS server is functional and has valid configured forwarders
```Powershell
PS C:\> Test-DnsServer -IPAddress 10.123.183.155 -Context Forwarder

IPAddress               Result                  RoundTripTime           TcpTried                UdpTried
---------               --------                 ------------           --------                --------
10.123.183.155           Success                 00:00:11                False                    True
```

This command tests whether the computer that has an IP address of 10.123.183.155 is a functional DNS server that has valid configured forwarders.

### Example 3: Test whether a DNS server is functional and has valid configured root hints
```Powershell
PS C:\> Test-DnsServer -IPAddress 10.123.183.155 -Context RootHints

IPAddress               Result                  RoundTripTime           TcpTried                UdpTried
---------               --------                 ------------           --------                --------
10.123.183.155           NoResponse              00:00:12                False                   True
```

This command tests whether the computer that has an IP address of 10.123.183.155 is a functional DNS server that has valid configured root hints.

### Example 4: Test whether a DNS server is functional and hosts the Contoso.com zone
```
PS C:\> Test-DnsServer -IPAddress 10.123.183.155 -ZoneName "Contoso.com"

IPAddress               Result                  RoundTripTime           TcpTried                UdpTried
---------               --------                 ------------           --------                --------
10.123.183.155           Success                 00:00:00                False                   True
```

This command tests whether the computer that has an IP address of 10.123.183.155 is a functional DNS server that hosts the Contoso.com zone.

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
The acceptable values for this parameter are: an IPv4 address; an IPv6 address; any other value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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

### -Context
Specifies functionalities to test.
Valid values are: DnsServer, Forwarder , and RootHints.

```yaml
Type: String
Parameter Sets: Context
Aliases:
Accepted values: DnsServer, Forwarder, RootHints

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddress
Specifies an array of DNS server IP addresses.

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

### -ZoneName
Specifies the name of the zone that the server hosts.

```yaml
Type: String
Parameter Sets: ZoneMaster
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerValidity[]

## NOTES

## RELATED LINKS

[Get-DnsServer](./Get-DnsServer.md)

[Set-DnsServer](./Set-DnsServer.md)

