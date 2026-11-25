---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerv6DnsSetting_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/set-dhcpserverv6dnssetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DhcpServerv6DnsSetting
---

# Set-DhcpServerv6DnsSetting

## SYNOPSIS
Configures how the DHCP server service updates the DNS server with the client-related information.

## SYNTAX

```
Set-DhcpServerv6DnsSetting [-ComputerName <String>] [-NameProtection <Boolean>]
 [-DeleteDnsRROnLeaseExpiry <Boolean>] [-DynamicUpdates <String>] [[-IPAddress] <IPAddress>]
 [[-Prefix] <IPAddress>] [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DhcpServerv6DnsSetting** cmdlet configures how the Dynamic Host Configuration Protocol (DHCP) server service updates the DNS server with the client-related information.
Specify the *Prefix* or *IPAddress* parameter together with at least one of the optional parameters.
Do not specify both *Prefix* and *IPAddress*.
If you specify neither *Prefix* or *IPAddress*, this cmdlet sets DNS update setting at the server level.

This cmdlet modifies the effective DNS update setting and sets it on the specified reservation, scope, or server level.

## EXAMPLES

### Example 1: Set server level DNS update settings
```
PS C:\> Set-DhcpServerv6DnsSetting -ComputerName "dhcpserver.contoso.com" -DynamicUpdates "Always" -DeleteDnsRRonLeaseExpiry $True
```

This example sets the DHCPv6 server level, or server-wide, DNS update configuration settings to always update DNS with leases entries, enables NAP protection by creating dynamic host configuration identifier (DHCID) resource records, and deletes the client entry from the DNS server when the lease expires.

### Example 2: Set DNS update settings for a scope
```
PS C:\> Set-DhcpServerv6DnsSetting -ComputerName "dhcpserver.contoso.com" -Prefix 2001:4898:7020:1020:: -DynamicUpdates "OnClientRequest" -NameProtection $True
```

This example sets the DNS update configuration settings for scope 2001:4898:7020:1020:: to update the DNS server with lease entries based on client request using the fully qualified domain name (FQDN) option (ID 81), and enables name protection by creating dynamic host configuration identifier (DHCID) resource records.

### Example 3: Set DNS update settings for an address
```
PS C:\> Set-DhcpServerv6DnsSetting -ComputerName dhcpserver.contoso.com -IPAddress 2001:4898:7020:1020::5 -DynamicUpdates Never
```

This example sets the DNS update configuration settings for the reserved IP address 2001:4898:7020:1020::5 to never update the DNS server for client lease entries.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
For more information about Windows PowerShell® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer that runs the DHCP server service.

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

### -DeleteDnsRROnLeaseExpiry
Specifies whether the DHCP server service deletes the DNS resource records for the DHCP client after the lease expires.
This parameter can only be set if the *DynamicUpdate* parameter is set to Always or OnClientRequest.

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

### -DynamicUpdates
Specifies the conditions under which to perform dynamic updates on the DNS server.
The acceptable values for this parameter are:

- Always.
The DHCP server service always performs dynamic DNS registration of A and PTR records for the DHCP clients.
- Never.
The DHCP server service does not perform any dynamic DNS registration.
- OnClientRequest.
The DHCP server service performs dynamic DNS registration of A and PTR records if the DHCP client has requested for the same in the DHCP client message.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Always, Never, OnClientRequest

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPAddress
Specifies the IPv6 address of the reservation on which the DNS update behavior is configured.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: ReservedIP

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NameProtection
Sets the enabled state for the name protection on the DHCP server service.
If you specify this parameter and there is an existing DNS record already by the same name, the DNS update for the client fails instead of being overwritten.

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

### -Prefix
Specifies the subnet prefix of the IPv6 scope on which the DNS update behavior is configured.

```yaml
Type: IPAddress
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6DnsSetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Reservation
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6DnsSetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DhcpServerv6DnsSetting](./Get-DhcpServerv6DnsSetting.md)

