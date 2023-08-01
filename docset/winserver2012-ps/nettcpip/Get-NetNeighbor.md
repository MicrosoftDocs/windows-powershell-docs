---
external help file: NetTCPIP_Cmdlets.xml
Module Name: NetTCPIP
online version: https://learn.microsoft.com/powershell/module/nettcpip/get-netneighbor?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetNeighbor

## SYNOPSIS
Gets information about the neighbor cache for IPv4 and IPv6.

## SYNTAX

```
Get-NetNeighbor [[-IPAddress] <String[]>] [-AddressFamily <AddressFamily[]>] [-AsJob]
 [-AssociatedIPInterface <CimInstance>] [-CimSession <CimSession[]>] [-InterfaceAlias <String[]>]
 [-InterfaceIndex <UInt32[]>] [-LinkLayerAddress <String[]>] [-PolicyStore <String>] [-State <State[]>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NetNeighbor** cmdlet gets the list of on-link neighbors and displays IP and link-layer address information about them in a table.
This includes properties such as the InterfaceIndex with which the neighbor is associated and the state of the entry.

The Neighbor cache maintains a list of information for each on-link neighbor, including the IP address and the associated link-layer address.
In IPv4, the neighbor cache is commonly known as an ARP cache.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NetNeighbor


The default output omits some properties. Run this cmdlet to display all of the fields (all of the properties of the object).
PS C:\>Get-NetNeighbor | Format-List -Property *
```

This example gets information about the neighbor cache for IPv4 and IPv6.

### EXAMPLE 2
```
PS C:\>Get-NetNeighbor -AddressFamily IPv6
```

This example gets information about the neighbor cache for neighbors that have an IPv6 address.

### EXAMPLE 3
```
PS C:\>Get-NetNeighbor -State Reachable | Get-NetAdapter
```

This example gets NetAdapter information for all of the adapters that have reachable neighbors.

## PARAMETERS

### -AddressFamily
Gets neighbor cache information only about a specific IP address family.
The acceptable values for this parameter are:

 -- IPv4: IPv4 Address information. 

 -- IPv6: IPv6 address information.

```yaml
Type: AddressFamily[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -AssociatedIPInterface
Gets neighbor cache information only about a specific network IP interface CIM object.
This is typically as input through the pipeline.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -IPAddress
Gets neighbor cache information only about a specific neighbor IP address.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LinkLayerAddress
Specifies the link layer address of the neighbor cache entry.
This is also known as a MAC address.
A link-layer address that uses IPv4 address syntax is a tunnel technology that encapsulates packets over an IPv4 tunnel, such as ISATAP or Teredo.
A link-layer address of all zeroes indicates that the neighbor is unreachable and the neighbor cache entry does not have a link-layer address entry.
An empty link-layer address indicates that the link layer does not use link-layer addresses, such as on a loopback interface.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyStore
Specifies the PolicyStore value.
The acceptable values for this parameter are:

 -- ActiveStore: The IP address information is currently valid. 

 -- PersistentStore: The IP address information is persistent across reboots.
When the computer starts, the PersistentStore settings are copied to the ActiveStore. 

The default value is ActiveStore.

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

### -InterfaceAlias
Gets neighbor cache information only about a specific interface, as defined by the InterfaceAlias.

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

### -InterfaceIndex
Gets neighbor cache information only about a specific interface, as defined by the InterfaceIndex number.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State
Gets neighbor cache information only about a specific state.
The Neighbor Cache contains information maintained by Neighbor Unreachability Detection.
A key piece of information is the reachability state of a neighbor.
The acceptable values for this parameter are:

 -- Unreachable: The IP address is unreachable. 

 -- Incomplete: Address resolution is in progress and the link-layer address of the neighbor has not yet been determined. 

 -- Probe: The neighbor is no longer known to be reachable, and unicast Neighbor Solicitation probes are being sent to verify reachability. 

 -- Delay: The neighbor is no longer known to be reachable, and traffic has recently been sent to the neighbor.
Rather than probe the neighbor immediately, however, the system will delay sending probes for a short while in order to give upper layer protocols a chance to provide reachability confirmation. 

 -- Stale: The neighbor is no longer known to be reachable but until traffic is sent to the neighbor, no attempt should be made to verify its reachability. 

 -- Reachable: The neighbor is known to have been reachable recently (within tens of seconds). 

 -- Permanent: The neighbor is statically provisioned and will not expire unless deleted through configuration. 

 -- Maximum: A maximum value for testing purposes.

```yaml
Type: State[]
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

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetNeighbor
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Format-List](https://go.microsoft.com/fwlink/p/?LinkId=113302)

[New-NetNeighbor](./New-NetNeighbor.md)

[Remove-NetNeighbor](./Remove-NetNeighbor.md)

[Set-NetNeighbor](./Set-NetNeighbor.md)

[Get-NetAdapter](../netadapter/Get-NetAdapter.md)

