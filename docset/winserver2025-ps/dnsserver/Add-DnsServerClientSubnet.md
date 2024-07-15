---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerClientSubnet_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/add-dnsserverclientsubnet?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DnsServerClientSubnet
---

# Add-DnsServerClientSubnet

## SYNOPSIS
Adds a client subnet to a DNS server.

## SYNTAX

```
Add-DnsServerClientSubnet [-Name] <String> [[-IPv4Subnet] <String[]>] [[-IPv6Subnet] <String[]>] [-PassThru]
 [-ComputerName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-DnsServerClientSubnet** cmdlet adds a client subnet to a Domain Name System (DNS) server.
A client subnet is a group of  IP subnets.
A client subnet is identified by a name.
A client subnet contains two lists of IP address, one for IPv4 subnets and one for IPv6 subnets.
A client subnet can represent a logical group, for example, a geographical area, a datacenter, or a trusted resolver fleet.
You can use client subnets in criteria in DNS policies.
Multiple DNS policies can refer to the same client subnet.

## EXAMPLES

### Example 1: Add a client subnet specified in IPv4
```
PS C:\> Add-DnsServerClientSubnet -Name "NorthAmericaSubnet" -IPv4Subnet 172.21.33.0/16 -PassThru
Name                                                                                       IPV4Subnet
----                                                                                       ----------
NorthAmericaSubnet                                                                         {172.21.33.0/16}
```

This command adds a client subnet named NorthAmericaSubnet to the DNS server.
The command specifies the subnet by using an IPv4 address.

### Example 2: Add a client subnet specified in IPv6
```
PS C:\> Add-DnsServerClientSubnet -Name "EuropeSubnet" -IPv6Subnet 0db8::1/28 -PassThru | Format-List
Name       : EuropeSubnet
IPV4Subnet :
IPV6Subnet : {3ffe::1/28}
```

This command adds a client subnet named EuropeSubnet to the DNS server.
The command specifies the subnet by using an IPv6 address.
The command uses the **Format-List** cmdlet to control the appearance of the output.
For more information, type `Get-Help Format-List`.

### Example 3: Add a client subnet specified in both IPv4 and IPv6
```
PS C:\> Add-DnsServerClientSubnet -Name "AsiaSubnet" -IPv6Subnet 0db8::1/28 -PassThru -IPv4Subnet 172.16.0.1/8 | Format-List
Name       : AsiaSubnet
IPV4Subnet : {172.0.0.1/8}
IPV6Subnet : {4ffe::1/28}
```

This command adds a client subnet named AsiaSubnet to the DNS server.
The command specifies the subnet by using both IPv4 and IPv6 addresses.

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

### -IPv4Subnet
Specifies an array of IPv4 subnet addresses in Classless Interdomain Routing (CIDR) notation.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv6Subnet
Specifies an array of IPv6 subnet addresses in CIDR notation.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Species the name of the new client subnet.

```yaml
Type: String
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

### Microsoft.Management.Infrastructure.CimInstance#DnsServerClientSubnet

## NOTES

## RELATED LINKS

[Get-DnsServerClientSubnet](./Get-DnsServerClientSubnet.md)

[Remove-DnsServerClientSubnet](./Remove-DnsServerClientSubnet.md)

[Set-DnsServerClientSubnet](./Set-DnsServerClientSubnet.md)

