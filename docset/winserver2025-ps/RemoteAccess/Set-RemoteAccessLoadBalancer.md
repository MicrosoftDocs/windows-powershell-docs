---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RemoteAccessLoadBalancer_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-remoteaccessloadbalancer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RemoteAccessLoadBalancer
---

# Set-RemoteAccessLoadBalancer

## SYNOPSIS
Configures load balancing on the Remote Access (RA) server or the cluster server.

## SYNTAX

### EnableLoadBalancing (Default)
```
Set-RemoteAccessLoadBalancer [-ComputerName <String>] [-PassThru] [-UseThirdPartyLoadBalancer]
 [-InternetDedicatedIPAddress] <String[]> [-InternalDedicatedIPAddress <String[]>]
 [-InternetVirtualIPAddress <String[]>] [-InternalVirtualIPAddress <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DisableLoadBalancing
```
Set-RemoteAccessLoadBalancer [-Disable] [-ComputerName <String>] [-Force] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ThirdPartyLoadBalancer
```
Set-RemoteAccessLoadBalancer [-ComputerName <String>] [-PassThru] -ThirdPartyLoadBalancer <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-RemoteAccessLoadBalancer** cmdlet configures load balancing for a Remote Access (RA) deployment.

 -- The **InternalDedicatedIPAddress** and **InternalVirtualIPAddress** parameters must be specified unless the server is configured with a single network adapter only.

 -- If the use of a third-party external load balancer is Enabled, then Windows network load balancing (NLB) is automatically Disabled, otherwise NLB is Enabled.

 -- When load balancing is enabled the IP-HTTPS prefix and the IPv6 prefix for VPN must be of length 59 bits.
The IP-HTTPS prefix can be configured using the **ClientIPv6Prefix** parameter in the Set-DAServer cmdlet.

 -- All servers in the cluster share the same RA configuration.

Note: If Windows load balancing is used then the Network Load Balancing role (NLB) needs to be installed prior to using this cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-RemoteAccessLoadBalancer -InternetDedicatedIPAddress "131.107.0.20/255.255.255.0" -InternalDedicatedIPAddress @("3ffe::2/64","10.0.0.2/255.255.255.0") -InternetVirtualIPAddress @("131.107.0.5/255.255.255.0","131.107.0.15/255.255.255.0") -InternalVirtualIPAddress @("3ffe::5/64","10.0.0.5/255.255.255.0") -PassThru
NlbNodeStatus            : edge2.corp.contoso.com
ThirdPartyLoadBalancer   : Disabled
InternetVirtualIPAddress : {131.107.0.5/255.255.255.0, 131.107.0.15/255.255.255.0}
InternalVirtualIPAddress : {3ffe::5/64, 10.0.0.5/255.255.255.0}
```

This example sets the NLB settings with Windows load balancer in edge topology.
Therefore the Internet address of the existing DA server located at 131.107.0.2 is promoted to be the internet virtual IP address of the load balanced cluster.
In this way, clients can still connect to the same external IP that they connected to without bothering about load balancing.

### EXAMPLE 2
```
PS C:\>Set-RemoteAccessLoadBalancer -InternetDedicatedIPAddress @("10.0.0.2/255.255.255.0","3ffe::2/64") -InternetVirtualIPAddress @("10.0.0.5/255.255.255.0", "3ffe::5/64") -PassThru
NlbNodeStatus            : edge1.corp.contoso.com
ThirdPartyLoadBalancer    : Disabled
InternetVirtualIPAddress    : {10.0.0.5/255.255.255.0, 3ffe::5/64}
InternalVirtualIPAddress    :
```

This example sets the NLB settings with Windows load balancer in single network adapter topology.
The corporate network is IPv4 and IPv6 enabled and therefore an array containing the IPv4 and IPv6 addresses for internet VIP and DIP is specified.
Since the DA server is behind an edge device, the internet VIPs and DIPs contain corporate network addresses.

### EXAMPLE 3
```
PS C:\>Set-RemoteAccessLoadBalancer -InternetDedicatedIPAddress "131.107.0.20/255.255.255.0" -InternalDedicatedIPAddress @("3ffe::2/64","10.0.0.2/255.255.255.0") -InternetVirtualIPAddress @("131.107.0.5/255.255.255.0","131.107.0.15/255.255.255.0") -InternalVirtualIPAddress @("3ffe::5/64","10.0.0.5/255.255.255.0") -PassThru -UseThirdPartyLoadBalancer
NlbNodeStatus            : edge2.corp.contoso.com
ThirdPartyLoadBalancer   : Enabled
InternetVirtualIPAddress : {131.107.0.5/255.255.255.0, 131.107.0.15/255.255.255.0}
InternalVirtualIPAddress : {3ffe::5/64, 10.0.0.5/255.255.255.0}
```

This example sets the NLB settings using third party load balancer.
The administrator will still have to manually configure the NLB device.

### EXAMPLE 4
```
PS C:\>Set-RemoteAccessLoadBalancer -ThirdPartyLoadBalancer Disabled -PassThru
NlbNodeStatus            : edge2.corp.contoso.com
ThirdPartyLoadBalancer   : Disabled
InternetVirtualIPAddress : {131.107.0.5/255.255.255.0, 131.107.0.15/255.255.255.0}
InternalVirtualIPAddress : {3ffe::5/64, 10.0.0.5/255.255.255.0}
```

This example disables the external load balancer for a Windows load balanced cluster.
The computer will now use the Windows load balancer to balance the load between servers.

### EXAMPLE 5
```
PS C:\>Set-RemoteAccessLoadBalancer -ThirdPartyLoadBalancer Enabled -PassThru
NlbNodeStatus            : edge2.corp.contoso.com
ThirdPartyLoadBalancer   : Enabled
InternetVirtualIPAddress : {131.107.0.5/255.255.255.0, 131.107.0.15/255.255.255.0}
InternalVirtualIPAddress : {3ffe::5/64, 10.0.0.5/255.255.255.0}
```

This example enables the external load balancer for a Windows load balanced cluster.
The computer will now use the external load balancer to balance the load between servers.

### EXAMPLE 6
```
PS C:\>Set-RemoteAccessLoadBalancer -Disable
Confirm
Disabling loadbalancing will disable cluster configuration. Do you want to continue?

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is ꞌYꞌ): Y
```

This example removes the NLB configuration.
DA configuration is also removed from all the servers except the one on which the cmdlet is run.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Specifies the IPv4 or IPv6 address, or host name, of the server on which the cmdlet runs.
If this parameter is specified, then the server is added to the load balanced cluster.

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

### -Disable
Disables load balancing.

```yaml
Type: SwitchParameter
Parameter Sets: DisableLoadBalancing
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: DisableLoadBalancing
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InternalDedicatedIPAddress
Specifies one or more IP addresses with subnet masks that will be used as the dedicated IP addresses (DIPs) for load balancing on the internal network adapter.

Specify the IPv4 address and subnet in the format IP_ADDR/SUBNET.
For IPv6 specify the prefix length along with the IP address.

```yaml
Type: String[]
Parameter Sets: EnableLoadBalancing
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InternalVirtualIPAddress
Specifies one or more IP addresses with subnet masks that will be used as the virtual IP addresses (VIPs) for load balancing on the internal network adapter.
These are usually the current IP addresses on the internal adapter of the server on which the cmdlet is run.

Specify the IPv4 address and subnet in the format IP_ADDR/SUBNET.
For IPv6 specify the prefix length along with the IP address.

If ISATAP is deployed in the internal network, then at least one of the IP addresses specified in this parameter should be present in the ISATAP name entry in DNS.

The NLS should resolve to at least one of the VIPs.

```yaml
Type: String[]
Parameter Sets: EnableLoadBalancing
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InternetDedicatedIPAddress
Specifies one or more IPv4 or IPv6 addresses with subnet masks that will be used as the DIPs for load balancing on the external network adapter.

Specify the IPv4 address and subnet in the format IP_ADDR/SUBNET.
For IPv6 specify the prefix length along with the IP address.

```yaml
Type: String[]
Parameter Sets: EnableLoadBalancing
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InternetVirtualIPAddress
Specifies one or more IP addresses with subnet masks that will be used as the VIPs for load balancing on the external network adapter and should include the IPsec tunnel endpoint IP addresses on the external adapter.

Specify the IPv4 address and subnet in the format IP_ADDR/SUBNET.
For IPv6 specify the prefix length along with the IP address.
If ISATAP is deployed in the internal network, then at least one of the IP addresses specified in the parameter should be present in the ISATAP name entry in DNS.
If the external adapter VIP addresses are not specified, then by default the IPsec tunnel endpoint IP addresses on the external adapter are used.

```yaml
Type: String[]
Parameter Sets: EnableLoadBalancing
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

### -ThirdPartyLoadBalancer
Specifies the enabled state of a third-party external load balancer.
The acceptable values for this parameter are:

 -- Enabled.

 -- Disabled.
Note: If external load balancing is Enabled and Teredo has been deployed, then all the external DIPs must be consecutive addresses.

```yaml
Type: String
Parameter Sets: ThirdPartyLoadBalancer
Aliases:
Accepted values: Enabled, Disabled

Required: True
Position: Named
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

### -UseThirdPartyLoadBalancer
Enables use of a third-party external load balancer for cluster traffic.
Note: If external load balancing is enabled and Teredo has been deployed, then all the external DIPs must be consecutive addresses.

```yaml
Type: SwitchParameter
Parameter Sets: EnableLoadBalancing
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

### System.String[]

### System.String

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#RemoteAccessLoadBalancer

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The RemoteAccessLoadBalancer object consists of the following properties:

The list of nodes in the cluster and the following properties for each node:

 -- IPv4 or IPv6 address or host name of the node.

 -- The load balancing status of each node.

 -- IPv4 address ranges configured on each node for the VPN static pool address assignment.

 -- Status of third party load balancer: Enabled or Disabled.

 -- The list of internet virtual IP addresses.

 -- The list of internal virtual IP addresses.

## NOTES

## RELATED LINKS

[Get-RemoteAccessLoadBalancer](./Get-RemoteAccessLoadBalancer.md)

[Remove-RemoteAccessLoadBalancerNode](./Remove-RemoteAccessLoadBalancerNode.md)

[Set-DAServer](./Set-DAServer.md)

[Set-RemoteAccessLoadBalancer](./Set-RemoteAccessLoadBalancer.md)

