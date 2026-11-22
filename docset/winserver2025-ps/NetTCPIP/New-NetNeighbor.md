---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetNeighbor.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nettcpip/new-netneighbor?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetNeighbor
---

# New-NetNeighbor

## SYNOPSIS
Creates a neighbor cache entry.

## SYNTAX

### ByInterfaceAlias (Default)
```
New-NetNeighbor [-IPAddress] <String> -InterfaceAlias <String> [-LinkLayerAddress <String>]
 [-PolicyStore <String>] [-State <State>] [-AddressFamily <AddressFamily>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInterfaceIndex
```
New-NetNeighbor [-IPAddress] <String> [-LinkLayerAddress <String>] [-PolicyStore <String>] [-State <State>]
 [-AddressFamily <AddressFamily>] -InterfaceIndex <UInt32> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetNeighbor** cmdlet creates a neighbor cache entry.
The neighbor cache maintains information for each on-link neighbor, including the IP address and the associated link-layer address.
The address family that you specify for the neighbor cache entry must match the address family of the IP interface.

## EXAMPLES

### Example 1: Create an IPv4 neighbor cache entry
```
PS C:\>New-NetNeighbor -InterfaceIndex 12 -IPAddress "192.168.0.5" -LinkLayerAddress "00-00-12-00-00-ff"
```

This command creates a neighbor cache entry that has the IP address 192.168.0.5.
The command specifies that the neighbor is connected to the interface that has the index 12.
The command specifies that the link-layer address of the neighbor cache entry is 00-00-12-00-00-ff.

### Example 2: Create an IPv6 neighbor cache entry
```
PS C:\>New-NetNeighbor -InterfaceIndex 13 -IPAddress "fe80::5efe:192.168.0.5"
```

This command creates a neighbor cache entry on a virtual ISATAP interface that has the IP address fe80::5efe:192.168.0.5.
The command specifies that the neighbor is connected to the interface that has the index 13.

## PARAMETERS

### -AddressFamily
Specifies the IP address family.
The cmdlet adds a neighbor cache entry that belongs to the IP address family you specify.
If you do not specify this parameter, the cmdlet automatically generates the address families of the neighbor cache entries.
The acceptable values for this parameter are:

- IPv4
- IPv6

```yaml
Type: AddressFamily
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
Specifies an IP address.
The cmdlet adds a neighbor cache entry that has the IP address you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterfaceAlias
Specifies the alias of a network interface.
The cmdlet adds a neighbor cache entry for the network interface that has the alias you specify.

```yaml
Type: String
Parameter Sets: ByInterfaceAlias
Aliases: ifAlias

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies the alias of a network interface.
The cmdlet adds a neighbor cache entry for the network interface located at the index you specify.

```yaml
Type: UInt32
Parameter Sets: ByInterfaceIndex
Aliases: ifIndex

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LinkLayerAddress
Specifies the link-layer address of the neighbor cache entry.
The cmdlet adds a neighbor cache entry that has the link-layer address you specify.

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

### -PolicyStore
Specifies a **PolicyStore** value.
The cmdlet adds a neighbor cache entry that has the **PolicyStore** value you specify.
The acceptable values for this parameter are:

- ActiveStore: The IP address information is valid.
- PersistentStore: The computer saves IP address information across restarts.
When the computer restarts, it copies the saved settings to the ActiveStore.

Specify ActiveStore only.

If you do not specify this parameter, the default entries are created in both the ActiveStore and the PersistentStore.

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
Specifies the state of the neighbor cache entry.
The cmdlet adds a neighbor cache entry that has the state you specify.
You can create only neighbor cache entries that are in a permanent state.
The acceptable values for this parameter are:

- Permanent.
The neighbor is statically provisioned and will not expire unless you remove it.

```yaml
Type: State
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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetNeighbor
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetAdapter](../netadapter/Get-NetAdapter.md)

[Get-NetNeighbor](./Get-NetNeighbor.md)

[Remove-NetNeighbor](./Remove-NetNeighbor.md)

[Set-NetNeighbor](./Set-NetNeighbor.md)

