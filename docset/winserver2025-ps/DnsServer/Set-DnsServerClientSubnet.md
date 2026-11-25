---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerClientSubnet_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/set-dnsserverclientsubnet?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DnsServerClientSubnet
---

# Set-DnsServerClientSubnet

## SYNOPSIS
Updates the IP addresses in a client subnet.

## SYNTAX

```
Set-DnsServerClientSubnet [-Name] <String> [[-IPv4Subnet] <String[]>] [[-IPv6Subnet] <String[]>]
 [-Action] <String> [-PassThru] [-ComputerName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsServerClientSubnet** cmdlet updates the IP addresses in a client subnet on a Domain Name System (DNS) server.
You can add, remove, or replace addresses.
You can modify the IPv4 addresses, IPv6 addresses, or both kinds of addresses.

## EXAMPLES

### Example 1: Add an IPv4 address to a client subnet
```
PS C:\> Add-DnsServerClientSubnet -Name "AsiaSubnet" -IPv6Subnet 0db8::1/28 -PassThru -IPv4Subnet 1.10.0.1/8
PS C:\> Set-DnsServerClientSubnet -Name "AsiaSubnet" -Action ADD -IPv4Subnet 192.168.0.4/16 -PassThru | Format-List

Name       : AsiaSubnet
IPV4Subnet : {10.10.0.1/8, 192.168.0.4/16}
IPV6Subnet : {0db8::1/28}
```

The first command creates a client subnet named AsiaSubnet by using the **Add-DnsServerClientSubnet** cmdlet.

The second command adds an IPv4 subnet to the AsiaSubnet client subnet.
The command uses the **Format-List** cmdlet to control the appearance of the output.
For more information, type `Get-Help Format-List`.

The command includes the *PassThru* parameter.
The added IPv4 address appears in the computer output.

### Example 2: Replace an IPv6 address in a client subnet
```
PS C:\> Add-DnsServerClientSubnet -Name "AsiaSubnet" -IPv6Subnet 0db8::1/28 -PassThru -IPv4Subnet 10.0.0.1/8
PS C:\> Set-DnsServerClientSubnet -Name "AsiaSubnet" -Action REPLACE -IPv6Subnet 0db8::1/8 -PassThru |  Format-List

Name       : AsiaSubnet
IPV4Subnet : {10.0.0.1/8}
IPV6Subnet : {0db8::1/8}
```

The first command creates a client subnet named AsiaSubnet that includes the IPv6 address 0db8::1/28.

The second command replaces the IPv6 addresses for the client subnet.
The computer output includes the address 0db8::1/8 in place of 0db8::1/28.

### Example 3: Remove an IPv4 address from a client subnet
```
PS C:\> Add-DnsServerClientSubnet -Name "AsiaSubnet" -IPv6Subnet 0db8::1/28 -PassThru -IPv4Subnet 10.0.0.1/8
PS C:\> Set-DnsServerClientSubnet -Name "AsiaSubnet" -Action REMOVE -IPv4Subnet 10.0.0.1/8 -PassThru | Format-List

Name       : AsiaSubnet
IPV4Subnet :
IPV6Subnet : {0db8::1/8}
```

The first command creates a client subnet named AsiaSubnet that includes both an IPv4 address and an IPv6 address.

The second command removes the IPv4 address.
The computer output displays only the IPv6 address.

## PARAMETERS

### -Action
Specifies whether to add to, remove, or replace the IP addresses in the client subnet.
The acceptable values for this parameter are:

- ADD
- REMOVE
- REPLACE

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: ADD, REMOVE, REPLACE

Required: True
Position: 2
Default value: None
Accept pipeline input: False
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
Specifies an array IPv4 subnet addresses in Classless Interdomain Routing (CIDR) notation.

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

### -IPv6Subnet
Specifies an array IPv6 subnet addresses in CIDR notation.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the client subnet to modify.

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

[Add-DnsServerClientSubnet](./Add-DnsServerClientSubnet.md)

[Get-DnsServerClientSubnet](./Get-DnsServerClientSubnet.md)

[Remove-DnsServerClientSubnet](./Remove-DnsServerClientSubnet.md)

