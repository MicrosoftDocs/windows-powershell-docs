---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetNeighbor.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nettcpip/get-netneighbor?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetNeighbor
---

# Get-NetNeighbor

## SYNOPSIS
Gets neighbor cache entries.

## SYNTAX

```
Get-NetNeighbor [[-IPAddress] <String[]>] [-InterfaceIndex <UInt32[]>] [-InterfaceAlias <String[]>]
 [-LinkLayerAddress <String[]>] [-State <State[]>] [-AddressFamily <AddressFamily[]>]
 [-AssociatedIPInterface <CimInstance>] [-PolicyStore <String>] [-IncludeAllCompartments]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetNeighbor** cmdlet gets neighbor cache entries.
The cmdlet returns information about IP addresses and link-layer addresses for the neighbor cache entries.

The neighbor cache maintains information for each on-link neighbor, including the IP address and the associated link-layer address.
In IPv4, the neighbor cache is commonly known as the Address Resolution Protocol (ARP) cache.

## EXAMPLES

### Example 1: Get all neighbor cache entries
```
PS C:\>Get-NetNeighbor
```

This command gets all the neighbor cache entries.
The default output for the cmdlet does not include all properties of the **NetNeighbor** object.

### Example 2: Output all properties for neighbor cache entries
```
PS C:\>Get-NetNeighbor | Format-List -Property *
```

This command gets all the neighbor cache entries.
The command uses the Format-List cmdlet to display all the properties in the output in the form of a table.
For more information, type `Get-Help Format-Table`.

### Example 3: Get neighbor cache entries that have an IPv6 address
```
PS C:\>Get-NetNeighbor -AddressFamily IPv6
```

This command gets information about the neighbor cache for neighbors that have an IPv6 address.

### Example 4: Get network adapters that have reachable neighbors
```
PS C:\>Get-NetNeighbor -State Reachable | Get-NetAdapter
```

This command gets a **NetNeighbor** object that contains neighbor cache entries that are reachable.
The command passes the **NetNeighbor** object to the **Get-NetAdapter** cmdlet by using the pipeline operator.
The **Get-NetAdapter** cmdlet gets the network adapters that have the interface index number for the network neighbors stored the **NetNeighbor** object.

## PARAMETERS

### -AddressFamily
Specifies an array of IP address families.
The cmdlet gets the neighbor cache entries that belong to the IP address families you specify.
The acceptable values for this parameter are:

- IPv4
- IPv6

```yaml
Type: AddressFamily[]
Parameter Sets: (All)
Aliases:
Accepted values: IPv4, IPv6

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -AssociatedIPInterface
Specifies an IP interface as a **CIM** object.
The cmdlet gets neighbor cache entries that belong to this interface.
To obtain an IP interface, use the Get-NetIPInterface cmdlet.

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

### -IPAddress
Specifies an array of IP addresses.
The cmdlet gets neighbor cache entries that have the IP addresses you specify.

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

### -IncludeAllCompartments
Indicates that the cmdlet includes neighbor cache entries from all configured network compartments.
If you do not specify this parameter, the cmdlet gets only neighbor cache entries in the default network compartment.

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

### -InterfaceAlias
Specifies an array of aliases of network interfaces.
The cmdlet gets neighbor cache entries for the network interfaces that have the aliases you specify.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: ifAlias

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies an array of indexes of network interfaces.
The cmdlet gets neighbor cache entries for the network interfaces located at the indexes you specify.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: ifIndex

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LinkLayerAddress
Specifies an array of link-layer addresses of the neighbor cache entry.
The cmdlet gets neighbor cache entries that have the link-layer addresses you specify.

The link-layer address is also called the media access control (MAC) address.
A link-layer address that uses IPv4 address syntax is a tunnel technology that encapsulates packets over an IPv4 tunnel, such as Intra-Site Automatic Tunnel Addressing Protocol (ISATAP) or Teredo.
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
Specifies a **PolicyStore** value.
The cmdlet gets neighbor cache entries that have the **PolicyStore** value you specify.
The acceptable values for this parameter are:

- ActiveStore.
The IP address information is valid.
- PersistentStore.
The computer saves IP address information across restarts.
When the computer restarts, it copies the saved settings to the ActiveStore.

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

### -State
Specifies an arrary of states of neighbor cache entries.
The cmdlet gets neighbor cache entries that have the state you specify.
The neighbor cache contains information maintained by Neighbor Unreachability Detection.
Neighbor Unreachability Detection for IPv4 tracks the reachable state of IPv4 nodes in the IPv4 route cache.
The acceptable values for this parameter are:

- Unreachable.
The IP address is unreachable.
- Incomplete.
Address resolution is in progress and Neighbor Unreachability Detection has not determined the link-layer address of the neighbor.
- Probe.
The neighbor is no longer known to be reachable, and Neighbor Unreachability Detection is sending unicast Neighbor Solicitation probes to verify reachability.
- Delay.
The neighbor is no longer known to be reachable, and traffic was recently sent to the neighbor.
Neighbor Unreachability Detection does not probe the neighbor immediately.
Neighbor Unreachability Detection delays sending probes for a short time  so that the upper layer protocols can provide reachability confirmation.
- Stale.
The neighbor is no longer known to be reachable.
and Until traffic is sent to the neighbor, Neighbor Unreachability Detection makes no attempt to verify its reachability.
- Reachable.
The neighbor is known to have been reachable recently, within the last minute.
- Permanent.
The neighbor is statically provisioned and will not expire unless you remove it  through configuration.
- Maximum.
A maximum value for testing purposes.

```yaml
Type: State[]
Parameter Sets: (All)
Aliases:
Accepted values: Unreachable, Incomplete, Probe, Delay, Stale, Reachable, Permanent

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetNeighbor
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetAdapter](../netadapter/Get-NetAdapter.md)

[New-NetNeighbor](./New-NetNeighbor.md)

[Remove-NetNeighbor](./Remove-NetNeighbor.md)

[Set-NetNeighbor](./Set-NetNeighbor.md)

