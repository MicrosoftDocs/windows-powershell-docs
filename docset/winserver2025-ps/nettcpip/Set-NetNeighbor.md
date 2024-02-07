---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetNeighbor.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nettcpip/set-netneighbor?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetNeighbor
---

# Set-NetNeighbor

## SYNOPSIS
Modifies a neighbor cache entry.

## SYNTAX

### ByName (Default)
```
Set-NetNeighbor [[-IPAddress] <String[]>] [-InterfaceIndex <UInt32[]>] [-InterfaceAlias <String[]>]
 [-State <State[]>] [-AddressFamily <AddressFamily[]>] [-PolicyStore <String>] [-IncludeAllCompartments]
 [-LinkLayerAddress <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetNeighbor -InputObject <CimInstance[]> [-LinkLayerAddress <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetNeighbor** cmdlet modifies a neighbor cache entry.
The neighbor cache maintains information for each on-link neighbor, including the IP address and the associated link-layer address.
You can modify only neighbor cache entries that are in a permanent state on interfaces that have link-layer addresses.
Use this cmdlet to modify the link-layer address and policy store setting of a neighbor cache entry.

## EXAMPLES

### Example 1: Set the link-layer address for a neighbor cache entry
```
PS C:\>Set-NetNeighbor -InterfaceIndex 12 -IPAddress "192.168.0.5" -LinkLayerAddress "00-00-12-00-00-ff"
```

This command sets the link-layer address for the neighbor cache entry that has the IP address 192.168.0.5 and the interface index value of 12.

### Example 2: Set the link-layer address for a neighbor cache entry by using an input object
```
PS C:\>Get-NetNeighbor -InterfaceIndex 12 -IPAddress "192.168.0.5" | Set-NetNeighbor -LinkLayerAddress "00-00-12-00-00-ff"
```

This command gets the **NetNeighbor** object that has the IP address 192.168.0.5 and the interface index value of 12.
The command passes the object to the **Set-NetNeighbor** cmdlet by using the pipeline operator.
**Set-NetNeighbor** sets the link-layer address for the neighbor cache entry to 00-00-12-00-00-ff.

## PARAMETERS

### -AddressFamily
Specifies an array of IP address families.
The cmdlet modifies the neighbor cache entries that belong to the IP address families you specify.
If you do not specify this parameter, the cmdlet automatically generates the address families of the neighbor cache entries.
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
The cmdlet modifies neighbor cache entries that have the IP addresses you specify.

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
If you do not specify this parameter, the cmdlet modifies only neighbor cache entries in the default network compartment.

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
The cmdlet modifies neighbor cache entries for the network interfaces that have the aliases you specify.

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
The cmdlet modifies neighbor cache entries for the network interfaces located at the indexes you specify.

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
Specifies the link-layer address of the neighbor cache entry.
The cmdlet modifies the link-layer address of the neighbor cache entry you specify.

The link-layer address is also called the media access control (MAC) address.
A link-layer address that uses IPv4 address syntax is a tunnel technology that encapsulates packets over an IPv4 tunnel, such as Intra-Site Automatic Tunnel Addressing Protocol (ISATAP) or Teredo.
A link-layer address of all zeroes indicates that the neighbor is unreachable and the neighbor cache entry does not have a link-layer address entry.
An empty link-layer address indicates that the link layer does not use link-layer addresses, such as on a loopback interface.

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
The cmdlet modifies the **PolicyStore** setting for the neighbor cache entry to the value you specify.
The acceptable values for this parameter are:

- ActiveStore: The IP address information is valid.
- PersistentStore: The computer saves IP address information across restarts.
When the computer restarts, it copies the saved settings to the ActiveStore.

Specify ActiveStore only.

If you do not specify this parameter, the default entries are created in both the ActiveStore and the PersistentStore.

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
Specifies an array of states of the neighbor cache entry.
The cmdlet modifies the neighbor cache entries that have the states you specify.
You can modify only neighbor cache entries that are in a permanent state.
The acceptable values for this parameter are:

- Permanent.
The neighbor is statically provisioned and will not expire unless you remove it.

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

[Get-NetNeighbor](./Get-NetNeighbor.md)

[New-NetNeighbor](./New-NetNeighbor.md)

[Remove-NetNeighbor](./Remove-NetNeighbor.md)

