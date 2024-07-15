---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamSubnet.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/add-ipamsubnet?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-IpamSubnet
---

# Add-IpamSubnet

## SYNOPSIS
Adds a subnet to IPAM.

## SYNTAX

```
Add-IpamSubnet [-Name] <String> [-NetworkId] <String> [-NetworkType <VirtualizationType>]
 [-AddressSpace <String>] [-Owner <String>] [-Description <String>] [-VlanId <UInt16[]>]
 [-VmmLogicalNetwork <String>] [-NetworkSite <String>] [-VirtualSubnetId <UInt32>]
 [-CustomConfiguration <String>] [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-IpamSubnet** cmdlet adds an IP subnet to an IP Address Management (IPAM) server.
Use the cmdlet to add a NonVirtualized, Provider or Customer IP subnet in IPAM.
If the network type of the subnet to add is Provider or NonVirtualized, the cmdlet will add it to the default address space, unless you specify an address space.
If the network type of the range to add is Customer, you must specify an address space.

You can associate virtualized subnets, either provider or customer, with a logical network and a network site.
These properties represent an abstraction of a physical network and are inherited by all ranges and addresses that map to this subnet.

## EXAMPLES

### Example 1: Add a subnet
```
PS C:\> Add-IpamSubnet -Name "Contoso_2" -NetworkId "10.12.0.0/16" -VlanId 13,10 -PassThru
Name                 : Contoso_2

NetworkId            : 10.12.0.0/16

NetworkType          : NonVirtualized

Overlapping          : False

NetworkSite          :

VmmLogicalNetwork    :

ProviderAddressSpace : Default

CustomerAddressSpace :

VlanId               : {13, 10}

Owner                :
```

This command adds an IPv4 subnet named Contoso_2 to the network ID 10.12.0.0/16 and associates it with VLAN 13,10.

The command includes the *PassThru* parameter, so it displays results to the console.

### Example 2: Add a subnet to the default address space
```
PS C:\> Add-IpamSubnet -Name "Contoso_3" -NetworkId "10.13.0.0/16" -NetworkType Provider -VmmLogicalNetwork Storage -NetworkSite "Site03" -VlanId 13,10 -PassThru

Name                 : Contoso_3

NetworkId            : 10.13.0.0/16

NetworkType          : Provider

Overlapping          : False

NetworkSite          : Site03

VmmLogicalNetwork    : Storage

ProviderAddressSpace : Default

CustomerAddressSpace :

VlanId               : {13, 10}

Owner                :
```

This command adds an IPV4 subnet named Contoso_3 with network type provider to the default address space.
The command also adds the IPV4 subnet to the network ID 10.13.0.0/16 and sets the NetworkSite name to Site03.

The command includes the *PassThru* parameter, so it displays results to the console.

### Example 3: Add a subnet for a customer network type
```
PS C:\> Add-IpamSubnet -Name "Contoso_4" -NetworkId "10.13.0.0/16" -NetworkType Customer -AddressSpace "NetCat" -VmmLogicalNetwork Storage -NetworkSite "Site03 -VirtualSubnetId 10 -PassThru
Name                 : Contoso_4

NetworkId            : 10.13.0.0/16

NetworkType          : Customer

Overlapping          : False

NetworkSite          : Site03

VmmLogicalNetwork    : Storage

ProviderAddressSpace : ContosoDatacenter

CustomerAddressSpace : NetCat

VlanId               : {13, 10}

Owner                :
```

This command adds an IPv4 subnet named Contoso_4 with the network and prefix of 10.13.0.0/16 and has the network type customer.
The command also sets the address space as NetCat and the network site as Site03.

The command includes the *PassThru* parameter, so it displays results to the console.

### Example 4: Add a subnet and attach metadata
```
PS C:\> Add-IpamSubnet -Name "Contosov6_10" -NetworkId 2001:db8::ff00/120 -CustomConfiguration "Country=United States;ADSite=Site01" | Format-List Name, NetworkId, Overlapping, CustomConfiguration
Name                : Contosov6_10

NetworkId           : 2001:db8::ff00/120

Overlapping         : False

CustomConfiguration : Country=United States;ADSite=Site01;
```

This command adds physical subnets named Contosov6_10 and attaches AD Site metadata to the subnets.

The command includes the *PassThru* parameter, so it displays results to the console.

## PARAMETERS

### -AddressSpace
Specifies an address space to which this IP address subnet belongs.
If you do not specify an address space, the cmdlet retrieves data for all address spaces configured in IPAM.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -CustomConfiguration
Specifies semicolon-separated (;) name/value pairs.
This parameter specifies custom metadata that is associated with the address space.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description
Specifies a description of the subnet.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the subnet.

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

### -NetworkId
Specifies the network and the prefix for the given subnet.
Specify the network ID in Classless Interdomain Routing (CIDR) notation in the format Network/Prefix.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkSite
Specifies a network site that is associated with a logical network and forms an abstraction of the physical network.
A logical network can contain many network sites.
This property is inherited by all ranges and addresses associated with the given subnet.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkType
Specifies an array of network types for the addresses to add.
The acceptable values for this parameter are:

- Provider
- Customer
- NonVirtualized

 If the value of the *AddressSpace* parameter is Default, then this parameter can take the value Provider or NonVirtualized.
If the value of the *AddressSpace* parameter is Provider, then the value of this parameter, if specified, must be Provider.
Specifying any other value for this parameter will result in an error.
Similarly, if the value of the *AddressSpace* parameter is Customer, then the value of this parameter, if specified, must be Customer.
Specifying any other value for this parameter will result in an error.

If you do not specify this parameter, the network type defaults to NonVirtualized.

```yaml
Type: VirtualizationType
Parameter Sets: (All)
Aliases:
Accepted values: NonVirtualized, Provider, Customer

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Owner
Specifies the name of an owner for the subnet.

```yaml
Type: String
Parameter Sets: (All)
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

### -VirtualSubnetId
Specifies a virtual subnet ID.
When you use network virtualization, this property, along with Customer address and Provider address is used to route packets to a particular customer virtual machine.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VlanId
Specifies an array of unique identifiers for virtual local area networks (VLAN).

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VmmLogicalNetwork
Specifies the abstraction of a physical network that describes a particular function in your environment such as backend or frontend.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## OUTPUTS

### CimInstance#ROOT/microsoft/ipam/MSFT_IPAM_Subnet
This cmdlet returns an object that represents an IP Subnet in IPAM Server.

## NOTES

## RELATED LINKS

[Export-IpamSubnet](./Export-IpamSubnet.md)

[Get-IpamSubnet](./Get-IpamSubnet.md)

[Import-IpamSubnet](./Import-IpamSubnet.md)

[Remove-IpamSubnet](./Remove-IpamSubnet.md)

[Set-IpamSubnet](./Set-IpamSubnet.md)

