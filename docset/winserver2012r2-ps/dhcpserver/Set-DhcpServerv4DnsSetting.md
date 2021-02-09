---
external help file: PS_DhcpServerv4DnsSetting_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
online version: 
schema: 2.0.0
title: Set-DhcpServerv4DnsSetting
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: C04BC137-7A78-4CA8-8CB5-C9118046BB02
---

# Set-DhcpServerv4DnsSetting

## SYNOPSIS
Configures how the Dynamic Host Configuration Protocol (DHCP) server service updates the DNS server with the client-related information.

## SYNTAX

```
Set-DhcpServerv4DnsSetting [-ComputerName <String>] [-NameProtection <Boolean>]
 [-UpdateDnsRRForOlderClients <Boolean>] [-DeleteDnsRROnLeaseExpiry <Boolean>] [-DynamicUpdates <String>]
 [[-IPAddress] <IPAddress>] [[-ScopeId] <IPAddress>] [-PassThru] [-PolicyName <String>]
 [-DisableDnsPtrRRUpdate <Boolean>] [-DnsSuffix <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DhcpServerv4DnsSetting** cmdlet configures how the Dynamic Host Configuration Protocol (DHCP) server service updates the DNS server with the client-related information.
This cmdlet modifies the effective DNS update setting and sets the setting on the server or the specified scope, policy or reservation.

Specify at least one parameter related to DNS update settings from the following parameters: 

- **DeleteDnsRROnLeaseExpiry**
- **DynamicUpdates**
- **NameProtection**
- **UpdateDnsRRForOlderClients**
- **DnsSuffix**
- **DisableDnsPtrRRUpdate**

If you do not specify any of the **ScopeId**, **IPAddress**, or **PolicyName** parameters along with the parameters for DNS update settings, then the specified DNS update settings are set for the server level.

If you specify **ScopeId**, the DNS settings are set for the scope.
If you specify **PolicyName**, the DNS settings are set for the server level policy.
If you specify both **ScopeId** and **PolicyName**, the DNS settings are set for the scope level policy.

If you specify **IPAddress**, the DNS settings are set for the reservation.
Do not specify **IPAddress** with **ScopeID** or **PolicyName**.

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

### EXAMPLE 4
```
PS C:\>Set-DhcpServerv4DnsSetting -ComputerName dhcpserver.contoso.com -DisableDnsPtrRRUpdates $True -PolicyName WorkgroupDevices
```

This example sets DNS update configuration settings for the server policy WorkgroupDevices to disable DNS dynamic updates for PTR records.
The command specifies the computer, named dhcpserver.contoso.com, that runs the DHCP server service.

### EXAMPLE 5
```
PS C:\>Set-DhcpServerv4DnsSetting -ComputerName dhcpserver.contoso.com -DnsSuffix guestdomain.com -PolicyName ForeignDevices
```

This example sets DNS update configuration settings for the server policy ForeignDevices to enable DNS registration of clients under the DNS suffix guestdomain.com.
The command specifies the computer, named dhcpserver.contoso.com, that runs the DHCP server service.

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
Aliases: Session

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

### -DisableDnsPtrRRUpdate
Indicates whether the DHCP server performs the dynamic DNS registration of only A records.
If this value is $True, the DHCP server performs registration for only A records.
If this value is $False, the server performs registration of both A and PTR records.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DnsSuffix
Specifies a guest DNS suffix for registering DHCP clients with the DNS server.
The string must contain at least one character and cannot exceed 256 characters.
Do not specify this parameter unless you specify the **PolicyName** parameter.

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
Accepted values: Always, Never, OnClientRequest

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
Aliases: ReservedIP

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

### -PolicyName
Specifies the name of a policy.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

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

