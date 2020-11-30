---
external help file: UnifiedRA_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 29EDECC7-DDDB-4880-9332-246DD3BA97E4
manager: dansimp
---

# Get-RemoteAccessLoadBalancer

## SYNOPSIS
Displays load balanced cluster settings.

## SYNTAX

```
Get-RemoteAccessLoadBalancer [[-EntrypointName] <String>] [-AsJob] [-Brief] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-ThrottleLimit <Int32>]
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

### -Brief
Suppresses the retrieval of node status.
When specified, only the host name of each node is returned.

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
Specifies the IPv4 or IPv6 address, or host name, of the server on which the cmdlet runs.

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

### -EntrypointName
Specifies the name of the entry point in the multi-site deployment for which the load balancing configuration should be retrieved.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
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

## INPUTS

### None

## OUTPUTS

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

