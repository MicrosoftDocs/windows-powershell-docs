---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerClientSubnet_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/get-dnsserverclientsubnet?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DnsServerClientSubnet
---

# Get-DnsServerClientSubnet

## SYNOPSIS
Gets client subnets for a DNS server.

## SYNTAX

```
Get-DnsServerClientSubnet [[-Name] <String>] [-ComputerName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsServerClientSubnet** cmdlet gets client subnets for a Domain Name System (DNS) server.
Specify a client subnet by name to see only that client subnet.

## EXAMPLES

### Example 1: Get all client subnets
```
PS C:\> Get-DnsServerClientSubnet | Format-List
Name       : NorthAmericaSubnet
IPV4Subnet : {172.21.0.0/12}
IPV6Subnet : 

Name       : AsiaSubnet
IPV4Subnet : {192.168.0.4/16}
IPV6Subnet : {0db8::1/8}

Name       : EuropeSubnet
IPV4Subnet : 
IPV6Subnet : {0db8::1/28}
```

This command gets all the client subnets on the DNS server.
The command uses the **Format-List** cmdlet to control the appearance of the output.
For more information, type `Get-Help Format-List`.

### Example 2: Get a named client subnet
```
PS C:\> Get-DnsServerClientSubnet -Name "AsiaSubnet" | Format-List
Name       : AsiaSubnet
IPV4Subnet : {196.168.0.4/16}
IPV6Subnet : { 0db8::1/8}
```

This command gets the client subnet named AsiaSubnet.

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

### -Name
Specifies the name of the client subnet to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerClientSubnet[]

## NOTES

## RELATED LINKS

[Add-DnsServerClientSubnet](./Add-DnsServerClientSubnet.md)

[Remove-DnsServerClientSubnet](./Remove-DnsServerClientSubnet.md)

[Set-DnsServerClientSubnet](./Set-DnsServerClientSubnet.md)

