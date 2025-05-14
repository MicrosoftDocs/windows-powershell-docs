---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RemoteAccessLoadBalancer_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-remoteaccessloadbalancer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RemoteAccessLoadBalancer
---

# Get-RemoteAccessLoadBalancer

## SYNOPSIS
Displays load balanced cluster settings.

## SYNTAX

```
Get-RemoteAccessLoadBalancer [-ComputerName <String>] [-Brief] [[-EntrypointName] <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RemoteAccessLoadBalancer** cmdlet displays the following:

 -- A list of servers in the cluster.

 -- The status of each server.

 -- The VPN IP address range for each server, if VPN is enabled.

 -- A list of the internal and external virtual IP addresses (VIPs) in the cluster.

 -- The status of the third-party load balancer.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-RemoteAccessLoadBalancer -EntryPointName Edge1_Site
NlbNodeStatus               : edge.corp.contoso.com

ThirdPartyLoadBalancer      : Disabled

InternetVirtualIPAddress    : {131.107.0.2/255.255.255.0}

InternalVirtualIPAddress    : {2006:2005:1::2/64}
```

This example retrieves the NLB status of the site named Edge1_Site.

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

### -Brief
Indicates that the cmdlet suppresses retrieving node status.
If you specify this parameter, the cmdlet returns only the host name of each node.

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

### -EntrypointName
Specifies the name of the entry point in the multi-site deployment for which the load balancing configuration should be retrieved.

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

[Add-RemoteAccessLoadBalancerNode](./Add-RemoteAccessLoadBalancerNode.md)

[Remove-RemoteAccessLoadBalancerNode](./Remove-RemoteAccessLoadBalancerNode.md)

[Set-RemoteAccessLoadBalancer](./Set-RemoteAccessLoadBalancer.md)

