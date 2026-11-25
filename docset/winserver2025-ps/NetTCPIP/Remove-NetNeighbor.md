---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetNeighbor.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nettcpip/remove-netneighbor?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-NetNeighbor
---

# Remove-NetNeighbor

## SYNOPSIS
Removes neighbor cache entries.

## SYNTAX

### ByName (Default)
```
Remove-NetNeighbor [[-IPAddress] <String[]>] [-InterfaceIndex <UInt32[]>] [-InterfaceAlias <String[]>]
 [-LinkLayerAddress <String[]>] [-State <State[]>] [-AddressFamily <AddressFamily[]>]
 [-AssociatedIPInterface <CimInstance>] [-PolicyStore <String>] [-IncludeAllCompartments]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Remove-NetNeighbor -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-NetNeighbor** cmdlet removes neighbor cache entries.
The neighbor cache maintains information for each on-link neighbor, including the IP address and the associated link-layer address.

## EXAMPLES

### Example 1: Remove unreachable neighbor cache entries
```
PS C:\>Remove-NetNeighbor -State Unreachable
```

This command removes all neighbor cache entries that are unreachable.

### Example 2: Remove neighbor cache entries associated with a network adapter
```
PS C:\>Get-NetAdapter | Where-Object -FilterScript {$_.LinkSpeed -Eq "100 Mbps"} | Remove-NetNeighbor -AddressFamily IPv4
```

This command gets a **NetAdapter** object that contains network adapters, and then passes the **NetAdapter** object to the Where-Object cmdlet by using the pipeline operator.
The **Where-Object** cmdlet filters the network adapters that have a link speed of 100 Mbps, and then passes the network **NetAdapter** object to the Remove-NetNeighbor cmdlet.
The Remove-NetNeighbor cmdlet  removes all neighbor cache entries that have IPv4 addresses and are associated with a network adapter that has a link speed of 100 Mbps.

## PARAMETERS

### -AddressFamily
Specifies an array of IP address families.
The cmdlet removes the neighbor cache entries that belong to the IP address families you specify.
The acceptable values for this parameter are:

- IPv4
- IPv6

```yaml
Type: AddressFamily[]
Parameter Sets: ByName
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
The cmdlet removes neighbor cache entries that belong to this interface.
To obtain an IP interface, use the Get-NetIPInterface cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByName
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

### -IPAddress
Specifies an array of IP addresses.
The cmdlet removes neighbor cache entries that have the IP addresses you specify.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeAllCompartments
Indicates that the cmdlet includes neighbor cache entries from all configured network compartments.
If you do not specify this parameter, the cmdlet removes only neighbor cache entries in the default network compartment.

```yaml
Type: SwitchParameter
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InterfaceAlias
Specifies an array of aliases of network interfaces.
The cmdlet removes neighbor cache entries for the network interfaces that have the aliases you specify.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: ifAlias

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies an array of indexes of network interfaces.
The cmdlet removes neighbor cache entries for the network interfaces located at the indexes you specify.

```yaml
Type: UInt32[]
Parameter Sets: ByName
Aliases: ifIndex

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LinkLayerAddress
Specifies an array of link-layer addresses of the neighbor cache entry.
The cmdlet removes the neighbor cache entries that have the link-layer addresses you specify.

The link-layer address is also called the media access control (MAC) address.
A link-layer address that uses IPv4 address syntax is a tunnel technology that encapsulates packets over an IPv4 tunnel, such as Intra-Site Automatic Tunnel Addressing Protocol (ISATAP) or Teredo.
A link-layer address of all zeroes indicates that the neighbor is unreachable and the neighbor cache entry does not have a link-layer address entry.
An empty link-layer address indicates that the link layer does not use link-layer addresses, such as on a loopback interface.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -PolicyStore
Specifies a **PolicyStore** value.
The cmdlet removes the neighbor cache entries that have the **PolicyStore** value you specify.
The acceptable values for this parameter are:

- ActiveStore: The IP address information is valid.
- PersistentStore: The computer saves IP address information across restarts.
When the computer restarts, it copies the saved settings to the ActiveStore.

```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State
Specifies an arrary of states of neighbor cache entries.
The cmdlet removes the neighbor cache entries that have the states you specify.
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
Parameter Sets: ByName
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetNeighbor
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NetAdapter](../netadapter/Get-NetAdapter.md)

[Get-NetNeighbor](./Get-NetNeighbor.md)

[New-NetNeighbor](./New-NetNeighbor.md)

[Set-NetNeighbor](./Set-NetNeighbor.md)

