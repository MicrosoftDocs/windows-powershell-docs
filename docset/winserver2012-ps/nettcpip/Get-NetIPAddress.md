---
external help file: NetTCPIP_Cmdlets.xml
Module Name: NetTCPIP
online version: https://learn.microsoft.com/powershell/module/nettcpip/get-netipaddress?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetIPAddress

## SYNOPSIS
Gets information about IP address configuration.

## SYNTAX

```
Get-NetIPAddress [[-IPAddress] <String[]>] [-AddressFamily <AddressFamily[]>] [-AddressState <AddressState[]>]
 [-AsJob] [-AssociatedIPInterface <CimInstance>] [-CimSession <CimSession[]>] [-InterfaceAlias <String[]>]
 [-InterfaceIndex <UInt32[]>] [-PolicyStore <String>] [-PreferredLifetime <TimeSpan[]>]
 [-PrefixLength <Byte[]>] [-PrefixOrigin <PrefixOrigin[]>] [-SkipAsSource <Boolean[]>]
 [-SuffixOrigin <SuffixOrigin[]>] [-ThrottleLimit <Int32>] [-Type <Type[]>] [-ValidLifetime <TimeSpan[]>]
```

## DESCRIPTION
The **Get-NetIPAddress** cmdlet gets the IP address information such as IPv4 addresses, IPv6 addresses and the IP interfaces with which addresses are associated. 

This cmdlet also gets the **PrefixLength**, also known as a subnet mask.
For more information on subnetting, see Subnetting on TechNethttp://technet.microsoft.com/library/bb726997.aspx (http://technet.microsoft.com/library/bb726997.aspx) on TechNet. 

This cmdlet does not get the gateway as that is a routing concept covered by the Get-NetRoute cmdlet.
For IP endpoints, the gateway specifies the forwarding address or the next hop IP address over which the set of addresses defined by the network destination and subnet mask are reachable. 

Without parameters, this cmdlet gets all of the IP address configuration information on the computer.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NetIPAddress -AddressFamily IPv6
```

This example gets information about IP address configuration for all IPv6 addresses on the computer.

### EXAMPLE 2
```
PS C:\>Get-NetIPAddress | Format-Table
```

This example gets information about IP address configuration, and it displays some of that information in a table.
The table format provides a convenient overview for computers with many IP addresses.

### EXAMPLE 3
```
PS C:\>Get-NetIPAddress -InterfaceIndex 12
```

This example gets information about IP address configuration for a specific interface index.

### EXAMPLE 4
```
PS C:\>Get-NetIPAddress | Sort-Object -Property InterfaceIndex | Format-Table
```

This example gets information about IP address configuration, sorts them numerically by the interface index in the cmdlet name, and then displays them in a table format.
This display can help you find IP address information by interface index.

### EXAMPLE 5
```
PS C:\>Get-NetIPAddress | Where-Object -FilterScript { $_.ValidLifetime -Lt ([TimeSpan]::FromDays(1)) }


Similarly, this cmdlet can be used to get information about IP address configuration for IP addresses that have an Infinite ValidLifetime.
PS C:\>Get-NetIPAddress | Where-Object -FilterScript { $_.ValidLifetime -Eq ([TimeSpan]::MaxValue) }
```

This example gets information about IP address configuration for IP addresses that have a ValidLifetime of less than one day.

## PARAMETERS

### -AddressFamily
Gets IP address information only about a specific IP address family.
The acceptable values for this parameter are:

 -- IPv4: IPv4 address information. 

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

### -AddressState
Gets information about the duplicate address detection (DAD) state for an IPv4 and IPv6 address.
This parameter can be used to filter this cmdlet output based on addresses that are valid and available for use.
The acceptable values for this parameter are:

 -- Invalid: IP address configuration information for addresses that are not valid and will not be used. 

 -- Tentative: IP address configuration information for addresses that are not used for communication, as the uniqueness of those IP addresses is being verified. 

 -- Duplicate: IP address configuration information for addresses for which a duplicate IP address has been detected and the current IP address will not be used. 

 -- Deprecated: IP address configuration information for addresses that will no longer be used to establish new connections, but will continue to be used with existing connections. 

 -- Preferred: IP address configuration information for addresses that are valid and available for use.

```yaml
Type: AddressState[]
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
Gets IP address information only about a specific network IP interface CIM object.
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

### -InterfaceAlias
Gets IP address information only about a specific interface, as defined by this parameter.

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
Gets IP address information only about a specific interface, as defined by this cmdlet number.

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

### -IPAddress
Gets the information about a specific IPv4 or IPv6 address.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
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
Gets IP address information by a specific preferred lifetime.
This parameter uses time as defined by the TimeSpanhttp://msdn.microsoft.com/library/system.timespan.aspx structure.

```yaml
Type: TimeSpan[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrefixLength
Gets the IP address information for IP addresses that have a specific prefix length.
This parameter defines the local subnet size, and is also known as a subnet mask.

```yaml
Type: Byte[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrefixOrigin
Gets the IP address information for IP addresses that have a specific prefix origin.
IP addresses are divided into two parts, the prefix and the suffix.
The address prefix identifies the network portion of an IP address, and the address suffix identifies the host portion.
The acceptable values for this parameter are:

 -- Manual: The IP address prefix was manually specified. 

 -- WellKnown: The IP address prefix is from a well-known source. 

 -- DHCP: The IP address prefix was provided by DHCP settings. 

 -- RouterAdvertisement: The IP address prefix was obtained through a router advertisement (RA).

```yaml
Type: PrefixOrigin[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipAsSource
Gets the IP address information for IP addresses that have the SkipAsSource flag set to True or False.
This parameter is used in a multiple IP address scenario in which the only the primary IP address for outgoing traffic.
The IP addresses that have this parameter set to True are not used for outgoing traffic and are not registered in DNS.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SuffixOrigin
Gets the IP address information for IP addresses that have a specific suffix origin.
IP addresses are divided into two parts, the prefix and the suffix.
The address prefix identifies the network portion of an IP address, and the address suffix identifies the host portion.
The acceptable values for this parameter are:

 -- Manual: The IP address prefix was manually specified. 

 -- WellKnown: The IP address suffix is from a well-known source. 

 -- DHCP: The IP address suffix was provided by DHCP settings. 

 -- Link: The IP address suffix was obtained from the link-layer address. 

 -- Random: The IP address suffix was obtained from a random source.

```yaml
Type: SuffixOrigin[]
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
Type: Type[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ValidLifetime
Gets IP address information by a specific valid lifetime.
This parameter uses time as defined by the TimeSpanhttp://msdn.microsoft.com/library/system.timespan.aspx structure.

```yaml
Type: TimeSpan[]
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIPAddress
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Format-List](https://go.microsoft.com/fwlink/p/?LinkId=113302)

[Format-Table](https://go.microsoft.com/fwlink/p/?LinkId=113303)

[Sort-Object](https://go.microsoft.com/fwlink/p/?LinkId=113403)

[Where-Object](https://go.microsoft.com/fwlink/p/?LinkId=113423)

[Get-NetRoute](./Get-NetRoute.md)

[New-NetIPAddress](./New-NetIPAddress.md)

[Remove-NetIPAddress](./Remove-NetIPAddress.md)

[Set-NetIPAddress](./Set-NetIPAddress.md)

