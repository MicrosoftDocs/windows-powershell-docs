---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_DnsClient.cdxml-help.xml
Module Name: DnsClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsclient/get-dnsclient?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DnsClient
---

# Get-DnsClient

## SYNOPSIS
Gets details of the network interfaces configured on a specified computer.

## SYNTAX

```
Get-DnsClient [-InterfaceIndex <UInt32[]>] [[-InterfaceAlias] <String[]>]
 [-ConnectionSpecificSuffix <String[]>] [-RegisterThisConnectionsAddress <Boolean[]>]
 [-UseSuffixWhenRegistering <Boolean[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsClient** cmdlet gets configuration details specific to the different network interfaces on a specified computer.

## EXAMPLES

### Example 1: Get the network interface configuration
```
PS C:\> Get-DnsClient
```

This command gets configuration details of network interfaces on a computer.

### Example 2: Set the DNS server IP addresses for a computer
```
PS C:\> $dnsClient1 = Get-DnsClient -InterfaceAlias "Wired Ethernet Connection"
PS C:\> Set-DnsClientServerAddress -InputObject $dnsClient1 -ServerAddresses ("10.0.0.1","10.0.0.2")

This is a version of the cmdlet using the pipeline.
PS C:\> Get-DnsClient | Set-DnsClientServerAddress -ServerAddresses ("10.0.0.1","10.0.0.2")
```

This command sets the DNS server IP addresses for all wired Ethernet connections on a computer.

### Example 3: Reset the DNS client to use the default DNS server addresses specified by DHCP
```
PS C:\> Get-DnsClient | Set-DnsClientServerAddress -ResetServerAddresses
```

This command resets all network interfaces to use DHCP-specified DNS server addresses.

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

### -ConnectionSpecificSuffix
Specifies the connection-specific suffixes that are to be appended.
This parameter is a per-connection DNS suffix which will be appended to the computer name to construct a Fully Qualified Domain Name (FQDN).
This FQDN will be used as the host name for name resolution by the DNS client.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Suffix

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterfaceAlias
Specifies the friendly name of the interface.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies the index number of the interface.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -RegisterThisConnectionsAddress
Specifies the registration policy for this interface.

This parameter indicates whether the computer should automatically register the IP address associated with this connection with the DNS server.

```yaml
Type: Boolean[]
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

### -UseSuffixWhenRegistering
Specifies the registration suffix policy for this interface.

This parameter indicates whether suffixes must be used while registering an IP address.

```yaml
Type: Boolean[]
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_DNSClient
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_DNSClientServerAddress
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetAdapter
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIPInterface
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_DNSClient
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Register-DnsClient](./Register-DnsClient.md)

[Set-DnsClient](./Set-DnsClient.md)

