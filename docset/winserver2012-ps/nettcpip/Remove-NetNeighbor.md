---
external help file: NetTCPIP_Cmdlets.xml
Module Name: NetTCPIP
online version: https://docs.microsoft.com/powershell/module/nettcpip/remove-netneighbor?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-NetNeighbor

## SYNOPSIS
Deletes a neighbor cache entry for IPv4 or IPv6.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-NetNeighbor [[-IPAddress] <String[]>] [-AddressFamily <AddressFamily[]>] [-AsJob]
 [-AssociatedIPInterface <CimInstance>] [-CimSession <CimSession[]>] [-InterfaceAlias <String[]>]
 [-InterfaceIndex <UInt32[]>] [-LinkLayerAddress <String[]>] [-PassThru] [-PolicyStore <String>]
 [-State <State[]>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-NetNeighbor [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-NetNeighbor** cmdlet deletes a neighbor cache entry for IPv4 or IPv6.
The neighbor cache maintains a list of information for each on-link neighbor, including the IP address and the associated MAC address.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-NetNeighbor -State Unreachable
```

This example deletes all neighbor cache entries that are unreachable.

### EXAMPLE 2
```
PS C:\>Get-NetAdapter | Where-Object -FilterScript {$_.LinkSpeed -Eq "100 Mbps"} | Remove-NetNeighbor -AddressFamily IPv4
```

This example deletes all neighbor cache entries that have IPv4 addresses and are associated with a network adapter that has a link speed of 100 Mbps.

## PARAMETERS

### -AddressFamily
Removes all neighbor cache entries that have a specific IP address family.
The acceptable values for this parameter are:

 -- IPv4: Removes all of the neighbor cache entries that have IPv4 addresses. 

 -- IPv6: Removes all of the neighbor cache entries that have IPv6 addresses.

```yaml
Type: AddressFamily[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Removes all of the neighbor cache entries that are associated with a specific network IP interface CIM object.
This is typically as input through a pipeline.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
Removes all of the neighbor cache entries that have a specific IP address.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LinkLayerAddress
Specifies the link-layer address of the neighbor cache entry.
This is also known as a MAC address.
A link-layer address that uses IPv4 address syntax is a tunnel technology that encapsulates packets over an IPv4 tunnel, such as ISATAP or Teredo.
A link-layer address of all zeroes indicates that the neighbor is unreachable and the neighbor cache entry does not have a link-layer address entry.
An empty link-layer address indicates that the link layer does not use link-layer addresses, such as on a loopback interface.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InterfaceAlias
Removes all of the neighbor cache entries that are connected to a specific interface, described by InterfaceAlias.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Removes all of the neighbor cache entries that are connected to a specific interface, described by InterfaceIndex.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### -PolicyStore
Specifies the PolicyStore value.
The acceptable values for this parameter are:

 -- ActiveStore: The IP address information is currently valid. 

 -- PersistentStore: The IP address information is persistent across reboots.
When the computer starts, the PersistentStore settings are copied to the ActiveStore. 

The default value is ActiveStore.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State
Removes all of the neighbor cache entries that are in a specific state.
The neighbor cache contains information maintained by Neighbor Unreachability Detection.
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetNeighbor
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/p/?LinkId=113423)

[Get-NetNeighbor](./Get-NetNeighbor.md)

[New-NetNeighbor](./New-NetNeighbor.md)

[Set-NetNeighbor](./Set-NetNeighbor.md)

[Get-NetAdapter](../netadapter/Get-NetAdapter.md)

