---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetIPAddress.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nettcpip/new-netipaddress?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetIPAddress
---

# New-NetIPAddress

## SYNOPSIS
Creates and configures an IP address.

## SYNTAX

### ByInterfaceAlias (Default)
```
New-NetIPAddress [-IPAddress] <String> -InterfaceAlias <String> [-DefaultGateway <String>]
 [-AddressFamily <AddressFamily>] [-Type <Type>] [-PrefixLength <Byte>] [-ValidLifetime <TimeSpan>]
 [-PreferredLifetime <TimeSpan>] [-SkipAsSource <Boolean>] [-PolicyStore <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInterfaceIndex
```
New-NetIPAddress [-IPAddress] <String> [-DefaultGateway <String>] [-AddressFamily <AddressFamily>]
 [-Type <Type>] [-PrefixLength <Byte>] [-ValidLifetime <TimeSpan>] [-PreferredLifetime <TimeSpan>]
 [-SkipAsSource <Boolean>] [-PolicyStore <String>] -InterfaceIndex <UInt32> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetIPAddress** cmdlet creates and configures an IP address.
To create a specific IP address object, specify either an IPv4 address or an IPv6 address, and an interface index or interface alias.
We recommend that you define the prefix length, also known as a subnet mask, and a default gateway.

If you run this cmdlet to add an IP address to an interface on which DHCP is already enabled, then DHCP is automatically disabled.
If Duplicate Address Detection (DAD) is enabled on the interface, the new IP address is not usable until DAD successfully finishes, which confirms the uniqueness of the IP address on the link.

## EXAMPLES

### Example 1: Add an IPv4 address
```
PS C:\>New-NetIPAddress -InterfaceIndex 12 -IPAddress 192.168.0.1 -PrefixLength 24 -DefaultGateway 192.168.0.5
PS C:\>Remove-NetIPAddress -IPAddress 192.168.0.1 -DefaultGateway 192.168.0.5
```

The first command adds a new IPv4 address to the network interface at index 12.
The *PrefixLength* parameter specifies the subnet mask for the IP address.
In this example, the *PrefixLength* of 24 equals a subnet mask of 255.255.255.0.
When you add an IPv4 address, the address specified for the Default Gateway must be in the same subnet as the IPv4 address that you add.
The second command removes the IPv4 address. To remove the IPv4 address, use the Remove-NetIPAddress cmdlet.

## PARAMETERS

### -AddressFamily
Specifies an IP address family.
The cmdlet creates an IP address for the family.
If you do not specify this parameter, the property is automatically generated.
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

### -DefaultGateway
Specifies the IPv4 address or IPv6 address of the default gateway for the host.
Default gateways provide a default route for TCP/IP hosts to use when communicating with other hosts on remote networks.

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

### -IPAddress
Specifies the IPv4 or IPv6 address to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: LocalAddress

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceAlias
Specifies an alias of a network interface.
The cmdlet creates an IP address for the alias.

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
Specifies an index of a network interface.
The cmdlet creates an IP address for the index.

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

### -PolicyStore
Specifies a **PolicyStore** value.
The acceptable values for this parameter are:

 -- ActiveStore.
The IP address information is valid.
 -- PersistentStore.
The computer saves IP address information across restarts.
When the computer restarts, it copies the saved settings to the ActiveStore.

The default value is ActiveStore.
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

### -PreferredLifetime
Specifies a preferred lifetime, as a **TimeSpan** object, for an IP address.
To obtain a **TimeSpan** object, use the New-TimeSpan cmdlet.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrefixLength
Specifies a prefix length.
This parameter defines the local subnet size, and is also known as a subnet mask.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipAsSource
Indicates whether an address is a primary IP address.
This parameter identifies the primary IP address for outgoing traffic in a multiple IP address scenario.
If this parameter is set to True, the addresses are not used for outgoing traffic and are not registered in DNS.

```yaml
Type: Boolean
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

### -Type
Specifies an IP address type.
The acceptable values for this parameter are:

 -- Unicast
 -- Anycast

The default value is Unicast.

```yaml
Type: Type
Parameter Sets: (All)
Aliases:
Accepted values: Unicast, Anycast

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ValidLifetime
Specifies a valid lifetime value, as a **TimeSpan** object, for an IP address.
To obtain a **TimeSpan** object, use the New-TimeSpan cmdlet.

```yaml
Type: TimeSpan
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIPAddress
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetIPAddress](./Get-NetIPAddress.md)

[Remove-NetIPAddress](./Remove-NetIPAddress.md)

[Remove-NetRoute](./Remove-NetRoute.md)

[Set-NetIPAddress](./Set-NetIPAddress.md)

