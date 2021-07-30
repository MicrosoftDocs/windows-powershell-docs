---
external help file: NetTCPIP_Cmdlets.xml
Module Name: NetTCPIP
online version: https://docs.microsoft.com/powershell/module/nettcpip/remove-netipaddress?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-NetIPAddress

## SYNOPSIS
Deletes an IP address and the configuration properties of that IP address.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-NetIPAddress [[-IPAddress] <String[]>] [-AddressFamily <AddressFamily[]>]
 [-AddressState <AddressState[]>] [-AsJob] [-CimSession <CimSession[]>] [-DefaultGateway <String>]
 [-InterfaceAlias <String[]>] [-InterfaceIndex <UInt32[]>] [-PassThru] [-PolicyStore <String>]
 [-PreferredLifetime <TimeSpan[]>] [-PrefixLength <Byte[]>] [-PrefixOrigin <PrefixOrigin[]>]
 [-SkipAsSource <Boolean[]>] [-SuffixOrigin <SuffixOrigin[]>] [-ThrottleLimit <Int32>] [-Type <Type[]>]
 [-ValidLifetime <TimeSpan[]>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-NetIPAddress [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-NetIPAddress** cmdlet deletes IP address and the configuration properties of that IP address.
To remove a specific IP address object, be sure to use the IPv4 Address parameter or IPv6 Address parameter.
Other parameters will remove all IP addresses with the matching property.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>New-NetIPAddress -InterfaceIndex 12 -IPAddress 192.168.0.1


The remove cmdlet then removes it.
PS C:\>Remove-NetIPAddress -IPAddress 192.168.0.1
```

This example adds a new IP address.

### EXAMPLE 2
```
PS C:\>Get-NetIPAddress -IPAddress 192.168.0.1 | Remove-NetIPAddress
```

This example provides an alternative method to EXAMPLE 1 that removes all of the IP addresses that have an IP address of 192.168.0.1.

### EXAMPLE 3
```
PS C:\>Remove-NetIPAddress -PrefixOrigin Manual
```

This example removes all of the IP addresses that have a manually configured prefix origin.

## PARAMETERS

### -AddressFamily
Removes all IP addresses that have a specific IP address family.
A read-only property.
The acceptable values for this parameter are:

 -- IPv4: IPv4 address information. 

 -- IPv6: IPv6 address information.

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

### -AddressState
Removes all the IP addresses that have a specific duplicate address detection (DAD) state for an IPv4 and IPv6 address.
A read-only property.
The acceptable values for this parameter are:

 -- Invalid: IP address configuration information for addresses that are not valid and will not be used. 

 -- Tentative: IP address configuration information for addresses that are not used for communication, as the uniqueness of those IP addresses is being verified. 

 -- Duplicate: IP address configuration information for addresses for which a duplicate IP address has been detected and the current IP address will not be used. 

 -- Deprecated: IP address configuration information for addresses that will no longer be used to establish new connections, but will continue to be used with existing connections. 

 -- Preferred: IP address configuration information for addresses that are valid and available for use.

```yaml
Type: AddressState[]
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

### -DefaultGateway
Specifies the IPv4 address or IPv6 address of the default gateway for the host to use.
Default gateways provide a default route for TCP/IP hosts to use when communicating with other hosts on remote networks.

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
Removes all of the IP addresses that have a specific interface, as defined by the InterfaceAlias.

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
Removes all of the IP addresses that have a specific interface, as defined by the InterfaceIndex number.

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

### -IPAddress
Removes all of the IP addresses that have a specific IPv4 or IPv6 address.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
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

### -PreferredLifetime
Removes all of the IP addresses that have a specific PreferredLifetime.
PreferredLifetime uses time as defined by the TimeSpanhttps://msdn.microsoft.com/library/system.timespan.aspx structure.

```yaml
Type: TimeSpan[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrefixLength
Identifies the IP address object by the PrefixLength.
The PrefixLength defines the local subnet size, and is also known as a subnet mask.

```yaml
Type: Byte[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipAsSource
Removes all of the IP addresses that have a SkipAsSource flag to True or False.
SkipAsSource is used in a multiple IP address scenario in which the only the primary IP address for outgoing traffic.
The IP addresses that have SkipAsSource set to True are not used for outgoing traffic and are not registered in DNS.

```yaml
Type: Boolean[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### -Type
Removes all of the IP addresses that have a specific type.
The acceptable values for this parameter are:

 -- Unicast: Marks the address as a unicast address. 

 -- Anycast: Marks the address as an anycast address. 

The default value is Unicast.

```yaml
Type: Type[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ValidLifetime
Removes all of the IP addresses that have a ValidLifetime.
ValidLifetime uses time as defined by the TimeSpanhttps://msdn.microsoft.com/library/system.timespan.aspx structure.

```yaml
Type: TimeSpan[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIPAddress
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NetIPAddress](./Get-NetIPAddress.md)

[New-NetIPAddress](./New-NetIPAddress.md)

[Set-NetIPAddress](./Set-NetIPAddress.md)

