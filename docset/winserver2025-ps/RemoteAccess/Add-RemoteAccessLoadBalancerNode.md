---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RemoteAccessLoadBalancerNode_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/add-remoteaccessloadbalancernode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-RemoteAccessLoadBalancerNode
---

# Add-RemoteAccessLoadBalancerNode

## SYNOPSIS
Adds a server to the load balancing cluster.

## SYNTAX

```
Add-RemoteAccessLoadBalancerNode [-RemoteAccessServer] <String> [-InternalInterface <String>]
 [-InternetInterface <String>] [-VpnIPAddressRange <String[]>] [-ComputerName <String>] [-Force] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-RemoteAccessLoadBalancerNode** cmdlet adds a server to the load balanced cluster:

 -- The server is added to the cluster to which the server on which the cmdlet is run, or to the server specified in the **ComputerName** parameter.

 -- When a server is added to cluster, Remote Access settings are replicated on the server to match the other servers in the cluster.
The Remote Access role and the Network Load Balancing (NLB) role should be installed on the server before adding it to the cluster.

 -- The internal and external adapters can be specified manually.
If no parameters are specified, then the cmdlet will attempt to detect settings automatically.

 -- The IPv6 prefix for IP-HTTPS should be `59` bits.
If IPv6 addressing is used for VPN, then the IPv6 prefix should be `59` bits.

 -- All the designed IPs on the server being added to the cluster must be in the same subnet as other servers in the cluster.

 -- If self-signed certificates are not being used, then certificates for IP-HTTPS and network location server (NLS) (if NLS is on DirectAccess (DA) Server) must be present on the new server.
Note: The subject name of certificate must be same as the respective certificates on the other computers in the cluster.

## EXAMPLES

### EXAMPLE 1
```
Create a load balanced cluster using the Set-RemoteAccessLoadBalancer cmdlet.
PS C:\>Set-RemoteAccessLoadBalancer -InternetDedicatedIPAddress "131.107.0.20/255.255.255.0" -InternalDedicatedIPAddress @("3ffe::2/64","10.0.0.2/255.255.255.0") -InternetVirtualIPAddress @("131.107.0.5/255.255.255.0","131.107.0.15/255.255.255.0") -InternalVirtualIPAddress @("3ffe::5/64","10.0.0.5/255.255.255.0")


Add the Edge2 server as a new node in this load balanced cluster.
PS C:\>$RemoteAccessNLB = Add-RemoteAccessLoadBalancerNode -RemoteAccessServer Edge2.corp.contoso.com -PassThru
Confirm
Certificate Iphttps cannot be located on the Remote Access server. Do you want DirectAccess to create and use a self-signed certificate?

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y

Confirm
Certificate NLS cannot be located on the Remote Access server. Do you want DirectAccess to create and use a self-signed certificate?

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y

WARNING: When adding a server (running the network location server using a self-signed certificate) to a cluster, point the network location server DNS entry to the internal DIP of each cluster server. After GPO updates, update the DNS entry again to the cluster VIP.

The cmdlet is run on Edge1 server and therefore the Edge2 server is added to the same cluster as the Edge1 server as shown in output of NlbNodeStatus.
PS C:\>$RemoteAccessNLB.NlbNodeStatus
{EDGE1.CORP.CONTOSO.COM, EDGE2.CORP.CONTOSO.COM}
```

This example creates a NLB Cluster and adding a new server to a load balanced cluster.

### EXAMPLE 2
```
If VPN is enabled, define a static address range for VPN. If this is being used in a script and the prompts are to be suppressed, then run this cmdlet with the **Force** parameter.
PS C:\>Add-RemoteAccessLoadBalancerNode -RemoteAccessServer edge3 -VpnIPAddressRange @("192.168.1.1","192.168.1.100") -PassThru
Confirm
Certificate Iphttps cannot be located on the Remote Access server. Do you want DirectAccess to create and use a self-signed certificate?

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y

Confirm
Certificate NLS cannot be located on the Remote Access server. Do you want DirectAccess to create and use a self-signed certificate?

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y

WARNING: When adding a server (running the network location server using a self-signed certificate) to a cluster, point the network location server DNS entry to the internal DIP of each cluster server. After GPO updates, update the DNS entry again to the cluster VIP.

HostName       : EDGE3
StatusCode     : In Progress
IPAddressRange :
IPv6Prefix     :
```

This example adds a new server to a load balanced cluster with VPN enabled.

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
Specifies the IPv4or IPv6 address, or host name of the computer, on which the Remote Access server computer specific tasks should be run.
If this parameter is specified, then it represents the cluster to which the server is added.

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

### -Force
Forces the command to run without asking for user confirmation.

When suppressed the cmdlet assumes user confirmation for the below mentioned changes.

 -- If self-signed NLS certificate is found on all other nodes in the cluster, then a self-signed certificate is created for this node.

 -- If self-signed SSL (IP-HTTPS) certificate is found on all other nodes in the cluster, then a self-signed certificate is created for this node.

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

### -InternalInterface
Specifies the name of the corporate network facing interface of the specified server.
If a name is not specified, then this cmdlet attempts to find the internal interface automatically.
For a single-network adapter configuration the same name is specified for both the internal and internet interfaces.

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

### -InternetInterface
Specifies the name of the internet facing interface of the specified server.
If a name is not specified, then this cmdlet attempts to find the internet interface automatically.
For a single-network adapter configuration the same name is specified for both the internal and internet interfaces.

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

### -RemoteAccessServer
Specifies the IPv4 or IPv6 address, or name, of a server.
The cmdlet adds the server to the load balanced cluster.

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

### -VpnIPAddressRange
Specifies the IP address range for allocation to VPN clients.
This parameter must be specified if VPN is enabled.
The range should not overlap with ranges configured on other servers in the cluster.

In a cluster, only static pool address assignment can be used.
DHCP is not supported.

```yaml
Type: String[]
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.String[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#RemoteAccessLoadBalancerNode

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The RemoteAccessLoadBalancerNode object consists of the following properties:

 -- The IPv4/IPv6 address or host name of the node that was added to the cluster.

 -- The load balancing status of the node.

 -- IPv4 address ranges configured on the node for VPN static pool address assignment.

## NOTES

## RELATED LINKS

[Remove-RemoteAccessLoadBalancerNode](./Remove-RemoteAccessLoadBalancerNode.md)

[Set-RemoteAccessLoadBalancer](./Set-RemoteAccessLoadBalancer.md)

