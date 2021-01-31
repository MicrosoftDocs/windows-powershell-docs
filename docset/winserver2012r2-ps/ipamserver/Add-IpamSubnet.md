---
external help file: IpamSubnet.cdxml-help.xml
Module Name: IpamServer
online version: 
schema: 2.0.0
title: Add-IpamSubnet
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: AFA2EB0B-3E4D-477F-8883-4C19CF40EF95
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

You can associate virtualized subnets, either provider or customer, with a logical network  and a network site.
These properties represent an abstraction of a physical network and are inherited by all ranges and addresses that map to this subnet.

## EXAMPLES

### Example 1: Add a subnet
```
PS C:\>Add-IpamSubnet -Name Contoso_2 -NetworkId 10.12.0.0/16 -VlanId 13,10 -PassThru

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

This command adds an IPv4 subnet and associates it with VLANs.

### Example 2: Add a subnet to the default address space
```
PS C:\>Add-IpamSubnet -Name Contoso_3 -NetworkId 10.13.0.0/16 -NetworkType Provider -VmmLogicalNetwork Storage -NetworkSite Site03 -VlanId 13,10 -PassThru

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

This command adds an IPV4 subnet with network type provider to the default address space.

### Example 3: Add a subnet for a customer network type
```
PS C:\>Add-IpamSubnet -Name Contoso_3 -NetworkId 10.13.0.0/16 -NetworkType Customer -AddressSpace NetCat -VmmLogicalNetwork Storage -NetworkSite Site03 -VirtualSubnetId 10 -PassThru

Name                 : Contoso_3

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

This command adds an IPv4 subnet with network type customer.

### Example 4: Add a subnet and attach metadata
```
PS C:\>Add-IpamSubnet -Name Contosov6_10 -NetworkId 2001:db8::ff00/120 -CustomConfiguration "Country=United States;ADSite=Site01" | Format-List Name, NetworkId, Overlapping, CustomConfiguration

Name                : Contosov6_10

NetworkId           : 2001:db8::ff00/120

Overlapping         : False

CustomConfiguration : Country=United States;ADSite=Site01;
```

This command adds physical subnets and attaches AD Site metadata to the subnets.

## PARAMETERS

### -AddressSpace
Specifies an address space to which this IP address subnet belongs.
If you not specify an address space, the cmdlet retrieves data for all address spaces configured in IPAM.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Default
Accept pipeline input: True (ByPropertyName)
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
Specifies semicolon-separated name/value pairs.
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
 --  Customer
 --  NonVirtualized

 If the value of the **AddressSpace** parameter is Default, then this parameter can take the value Provider or NonVirtualized.
If the value of the **AddressSpace** parameter is Provider, then the value of this parameter, if specified, must be Provider.
Specifying any other value for this parameter will result in an error.
Similarly, if the value of the **AddressSpace** parameter is Customer, then the value of this parameter, if specified, must be Customer.
Specifying any other value for this parameter will result in an error.

If you do not specify this parameter, the network type defaults to NonVirtualized.

```yaml
Type: VirtualizationType
Parameter Sets: (All)
Aliases: 
Accepted values: NonVirtualized, Provider, Customer

Required: False
Position: Named
Default value: NonVirtualized
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
When you use network virtualization, this property, along with Customer address and Provider address is used to route packets to a particular customer VM.

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
Specifies an array of unique identifiers for VLANs.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### CimInstance#ROOT/microsoft/ipam/MSFT_IPAM_Subnet
Represents an IP Subnet in IPAM Server.

## NOTES

## RELATED LINKS

[Export-IpamSubnet](./Export-IpamSubnet.md)

[Get-IpamSubnet](./Get-IpamSubnet.md)

[Import-IpamSubnet](./Import-IpamSubnet.md)

[Remove-IpamSubnet](./Remove-IpamSubnet.md)

[Set-IpamSubnet](./Set-IpamSubnet.md)

