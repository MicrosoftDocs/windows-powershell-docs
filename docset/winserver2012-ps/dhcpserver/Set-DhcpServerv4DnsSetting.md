---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://learn.microsoft.com/powershell/module/dhcpserver/set-dhcpserverv4dnssetting?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DhcpServerv4DnsSetting

## SYNOPSIS
Configures how the Dynamic Host Configuration Protocol (DHCP) server service updates the DNS server with the client-related information.

## SYNTAX

```
Set-DhcpServerv4DnsSetting [[-ScopeId] <IPAddress>] [[-IPAddress] <IPAddress>] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-DeleteDnsRROnLeaseExpiry <Boolean>]
 [-DynamicUpdates <String>] [-NameProtection <Boolean>] [-PassThru] [-ThrottleLimit <Int32>]
 [-UpdateDnsRRForOlderClients <Boolean>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-DhcpServerv4DnsSetting** cmdlet configures how the Dynamic Host Configuration Protocol (DHCP) server service updates the DNS server with the client-related information.
The **ScopeId** or **IPAddress** parameter must be specified with at least one of the optional parameters.

The **ScopeId** and **IPAddress** parameters cannot both be specified.

If neither the **ScopeId** nor **IPAddress** parameter is specified, then the specified DNS update settings are set to the server level.

This cmdlet modifies the effective DNS update setting and sets the setting on the specified reservation, scope or server.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-DhcpServerv4DnsSetting -ComputerName dhcpserver.contoso.com -DynamicUpdates Always -DeleteDnsRRonLeaseExpiry True
```

This example sets the server level, or server-wide, DNS update configuration settings to always update DNS with leases entries and deletes the client entry from DNS when the lease expires.

### EXAMPLE 2
```
PS C:\>Set-DhcpServerv4DnsSetting -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0 -DynamicUpdates OnClientRequest -NameProtection True
```

This example sets the DNS update configuration settings for scope 10.10.10.0 to update the DNS with leases entries based on client request, indicated in the FQDN option (option ID 81), and enables name protection by creating dynamic host configuration identifier (DHCID) resource records.

### EXAMPLE 3
```
PS C:\>Set-DhcpServerv4DnsSetting -ComputerName dhcpserver.contoso.com -IPAddress 10.10.10.5 -DynamicUpdates Never
```

This example sets the DNS update configuration settings for the reserved IP address 10.10.10.5 to never update the DNS for client lease entries.
This cmdlet clears all of the properties other than the property that is specified.

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
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the DHCP server service.

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

### -DeleteDnsRROnLeaseExpiry
Specifies that the DHCP server service should delete the DNS resource records for the client after the lease expires. 
The acceptable values for this parameter are: True or False.
This parameter can only be set if the **DynamicUpdate** parameter is set to Always or OnClientRequest.

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
The acceptable values for this parameter are: Always, Never, or OnClientRequest. 

 - Always: The DHCP server service will always perform dynamic DNS registration of A and PTR records for the clients. 

 - Never: The DHCP server service will not perform any dynamic DNS registration 

 - OnClientRequest: The DHCP server service will perform dynamic DNS registration of A and PTR records if the client has requested the same in the DHCP client message.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPAddress
Specifies the IPv4 address of the reservation for which the specified DNS update settings are being set.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NameProtection
Specifies the enabled state for the DNS name protection on the DHCP server service. 

If this parameter is set to True, then DNS name protection is enabled.
If this parameter is set to True and there is an existing DNS record matching the name, then the DNS update for the client will fail instead of being overwritten.

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

### -ScopeId
Specifies the scope identifier, in IPv4 address format, for which the DNS update settings are being set.

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

### -UpdateDnsRRForOlderClients
Specifies the enabled state for the DNS registration of A and PTR records for older clients which do not request DNS updates.

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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4DnsSetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Reservation
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4DnsSetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DhcpServerv4DnsSetting](./Get-DhcpServerv4DnsSetting.md)

