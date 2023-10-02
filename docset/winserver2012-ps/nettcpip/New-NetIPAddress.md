---
external help file: NetTCPIP_Cmdlets.xml
Module Name: NetTCPIP
online version: https://learn.microsoft.com/powershell/module/nettcpip/new-netipaddress?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-NetIPAddress

## SYNOPSIS
Creates an IP address and the configuration properties of that IP address.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-NetIPAddress [-IPAddress] <String> [-AddressFamily <AddressFamily>] [-AsJob] [-CimSession <CimSession[]>]
 [-DefaultGateway <String>] [-PolicyStore <String>] [-PreferredLifetime <TimeSpan>] [-PrefixLength <Byte>]
 [-SkipAsSource <Boolean>] [-ThrottleLimit <Int32>] [-Type <Type>] [-ValidLifetime <TimeSpan>]
 -InterfaceAlias <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
New-NetIPAddress [-IPAddress] <String> [-AddressFamily <AddressFamily>] [-AsJob] [-CimSession <CimSession[]>]
 [-DefaultGateway <String>] [-PolicyStore <String>] [-PreferredLifetime <TimeSpan>] [-PrefixLength <Byte>]
 [-SkipAsSource <Boolean>] [-ThrottleLimit <Int32>] [-Type <Type>] [-ValidLifetime <TimeSpan>]
 -InterfaceIndex <UInt32> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **New-NetIPAddress** cmdlet creates IP address and the configuration properties of that IP address.
To create a specific IP address object, the required parameters include an IP address (IPv4 or IPv6) and an interface (InterfaceIndex or InterfaceAlias).
It is also recommended to define the prefix length, also known as a subnet mask, and default gateway.

If DHCP is enabled on the interface to which this cmdlet is configured to, then DHCP will automatically be disabled.

Note: The **DefaultGateway** parameter sets a route to make the new IP address reachable.
The Remove-NetIPAddress cmdlet will also remove this route provided the **DefaultGateway** parameter.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>New-NetIPAddress -InterfaceIndex 12 -IPAddress 192.168.0.1 -PrefixLength 24 -DefaultGateway 192.168.0.5


This command removes the IPv4 address. To remove the IPv4 address, use the Remove-NetIPAddress cmdlet.
PS C:\>Remove-NetIPAddress -IPAddress 192.168.0.1 -DefaultGateway 192.168.0.5
```

This command adds a new IPv4 address to the network interface at index 12.
The subnet mask is determined by the **PrefixLength** parameter.
In this example, the PrefixLength of 24 is equivalent to a subnet mask of 255.255.255.0. 
When you add an IPv4 address, the address specified for the Default Gateway must be in the same subnet as the IPv4 address you add.

## PARAMETERS

### -AddressFamily
Specifies an IP address family.
This property is automatically generated if unspecified.
The acceptable values for this parameter are:

 -- IPv4: IPv4 Address information. 

 -- IPv6: IPv6 address information.

```yaml
Type: AddressFamily
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

### -DefaultGateway
Specifies the IPv4 address or IPv6 address of the default gateway for the host to use.
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

### -InterfaceAlias
Specifies an IP interface for the IP address, as defined by the InterfaceAlias.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies an IP interface for the IP address, as defined by the InterfaceIndex number.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPAddress
Creates a specific IPv4 or IPv6 address.

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

### -PreferredLifetime
Specifies a PreferredLifetime.
PreferredLifetime uses time as defined by the TimeSpanhttp://msdn.microsoft.com/library/system.timespan.aspx structure.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Infinite
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrefixLength
Specifies a PrefixLength.
The PrefixLength defines the local subnet size, and is also known as a subnet mask.

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
Specifies the SkipAsSource flag.
SkipAsSource is used in a multiple IP address scenario in which the only the primary IP address for outgoing traffic.
The IP addresses that have SkipAsSource set to True are not used for outgoing traffic and are not registered in DNS.

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
Specifies a specific IP address type.
The acceptable values for this parameter are:

 -- Unicast: Marks the address as a unicast address. 

 -- Anycast: Marks the address as an anycast address. 

The default value is Unicast.

```yaml
Type: Type
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ValidLifetime
Specifies the ValidLifetime.
ValidLifetime uses time as defined by the TimeSpanhttp://msdn.microsoft.com/library/system.timespan.aspx structure.

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

