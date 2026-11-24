---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetIPAddress.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nettcpip/set-netipaddress?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetIPAddress
---

# Set-NetIPAddress

## SYNOPSIS
Modifies the configuration of an IP address.

## SYNTAX

### Query (cdxml) (Default)
```
Set-NetIPAddress [[-IPAddress] <String[]>] [-InterfaceIndex <UInt32[]>] [-InterfaceAlias <String[]>]
 [-AddressFamily <AddressFamily[]>] [-Type <Type[]>] [-PrefixOrigin <PrefixOrigin[]>]
 [-SuffixOrigin <SuffixOrigin[]>] [-AddressState <AddressState[]>] [-PolicyStore <String>]
 [-IncludeAllCompartments] [-PrefixLength <Byte>] [-ValidLifetime <TimeSpan>] [-PreferredLifetime <TimeSpan>]
 [-SkipAsSource <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetIPAddress -InputObject <CimInstance[]> [-PrefixLength <Byte>] [-ValidLifetime <TimeSpan>]
 [-PreferredLifetime <TimeSpan>] [-SkipAsSource <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetIPAddress** cmdlet modifies IP address configuration properties of an existing IP address.

To create an IPv4 address or IPv6 address, use the New-NetIPAddress cmdlet.

## EXAMPLES

### Example 1: Modify an IP address
```
PS C:\> New-NetIPAddress -InterfaceIndex 12 -IPAddress 192.168.0.1
PS C:\> Set-NetIPAddress -InterfaceIndex 12 -IPAddress 192.168.0.1 -PrefixLength 24
```

This command adds the IP address 192.168.0.1 to the interface located at index 12.

The **PrefixLength** parameter may also be specified as part of the Set-NetIPAddress cmdlet.

### Example 2: Modify an IP address and set the valid lifetime
```
PS C:\> $Timesp = ( New-TimeSpan -Days 1 )
PS C:\> Set-NetIPAddress -InterfaceIndex 12 -IPAddress 192.168.0.1 -PreferredLifetime $Timesp
```

The first command creates a new **TimeSpan** object of one day, and stores it in the variable named $Timesp.

The second command then uses the **TimeSpan** object to set the preferred lifetime of the IP address located at interface 12 to one day.

## PARAMETERS

### -AddressFamily
Specifies an array of IP address families.
The cmdlet modifies the IP address configuration that matches the families.
The acceptable values for this parameter are:

 -- IPv4
 -- IPv6

```yaml
Type: AddressFamily[]
Parameter Sets: Query (cdxml)
Aliases:
Accepted values: IPv4, IPv6

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddressState
Specifies an array of duplicate address detection (DAD) state values for the IP address.
The acceptable values for this parameter are:

- Invalid.
IP address configuration information for addresses that are not valid and will not be used.
- Tentative.
IP address configuration information for addresses that are not used for communication, as the uniqueness of those IP addresses is being verified.
- Duplicate.
IP address configuration information for addresses for which a duplicate IP address has been detected and the current IP address will not be used.
- Deprecated.
IP address configuration information for addresses that will no longer be used to establish new connections, but will continue to be used with existing connections.
- Preferred.
IP address configuration information for addresses that are valid and available for use.

```yaml
Type: AddressState[]
Parameter Sets: Query (cdxml)
Aliases:
Accepted values: Invalid, Tentative, Duplicate, Deprecated, Preferred

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
Specifies an array of IPv4 or IPv6 addresses.

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
Aliases: LocalAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeAllCompartments
Indicates that the cmdlet includes addresses from all configured network compartments.
If you do not specify this parameter, the cmdlet modifies only addresses in the default network compartment.

```yaml
Type: SwitchParameter
Parameter Sets: Query (cdxml)
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
The cmdlet modifies IP addresses that match the aliases.

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
Aliases: ifAlias

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies an array of indexes of network interfaces.
The cmdlet modifies IP addresses that match the indexes.

```yaml
Type: UInt32[]
Parameter Sets: Query (cdxml)
Aliases: ifIndex

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
Parameter Sets: Query (cdxml)
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

### -PrefixOrigin
ps_deprecate_para

```yaml
Type: PrefixOrigin[]
Parameter Sets: Query (cdxml)
Aliases:
Accepted values: Other, Manual, WellKnown, Dhcp, RouterAdvertisement

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipAsSource
Indicates whether an address is a primary IP address.
This parameter identifies the primary IP address for outgoing traffic in a multiple IP address scenario.
If this parameter is set to True, the address is not used for outgoing traffic and is not registered in DNS.

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

### -SuffixOrigin
Specifies an array of origins for address suffixes.
IP addresses are divided into two parts, the prefix and the suffix.
The address prefix identifies the network portion of an IP address, and the address suffix identifies the host portion.
The acceptable values for this parameter are:

 -- Manual.
The IP address suffix was manually specified.
 -- WellKnown.
The IP address suffix is from a well-known source.
 -- DHCP.
The IP address suffix was provided by DHCP settings.
 -- Link.
The IP address suffix was obtained from the link-layer address.
 -- Random.
The IP address suffix was obtained from a random source.

```yaml
Type: SuffixOrigin[]
Parameter Sets: Query (cdxml)
Aliases:
Accepted values: Other, Manual, WellKnown, Dhcp, Link, Random

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
Specifies an array of IP address types.
The acceptable values for this parameter are:

 -- Unicast
 -- Anycast

The default value is Unicast.

```yaml
Type: Type[]
Parameter Sets: Query (cdxml)
Aliases:
Accepted values: Unicast, Anycast

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ValidLifetime
Specifies a valid lifetime, as a **TimeSpan** object, for an IP address.
To obtain a **TimeSpan** object, use the **New-TimeSpan** cmdlet.

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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIPAddress
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[New-TimeSpan](https://go.microsoft.com/fwlink/p/?LinkId=113360)

[Get-NetIPAddress](./Get-NetIPAddress.md)

[New-NetIPAddress](./New-NetIPAddress.md)

[Remove-NetIPAddress](./Remove-NetIPAddress.md)

