---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamSubnet.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/get-ipamsubnet?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IpamSubnet
---

# Get-IpamSubnet

## SYNOPSIS
Gets a set of subnets from IPAM.

## SYNTAX

### ById
```
Get-IpamSubnet -NetworkId <String[]> [-NetworkType <VirtualizationType[]>] [-AddressSpace <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByAF
```
Get-IpamSubnet [-AddressFamily] <AddressFamily[]> [-NetworkType <VirtualizationType[]>]
 [-AddressSpace <String[]>] [-Unmapped] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByBlock
```
Get-IpamSubnet -MappingToBlock <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamSubnet** cmdlet gets a set of IP subnets from IP Address Management (IPAM).
By default, the cmdlet gets all IP addresses of a given address family from all address spaces configured in IPAM.
Use the *NetworkType* and *AddressSpace* parameters to filter the result for Provider and Customer subnets, or NonVirtualized subnets.

This cmdlet also provides parameter sets to retrieve all subnets that map to a given IP address block.

## EXAMPLES

### Example 1 Get all overlapping subnets
```
PS C:\> Get-IpamSubnet -AddressFamily IPv4 -AddressSpace "Default" | where {$_.Overlapping -eq $false}
```

This command gets all overlapping subnets in the default address space, including Provider and NonVirtualized subnets in the default address space.

### Example 2: Get all non-virtualized subnets in a site
```
PS C:\> Get-IpamSubnet -AddressFamily IPv4 -NetworkType NonVirtualized | where {$_.CustomConfiguration -Like "*ADSite=Contoso*"}| Format-List Name, NetworkId, CustomConfiguration
Name                : Contoso_1

NetworkId           : 10.10.0.0/16

CustomConfiguration : ADSite=Contoso;
Name                : Contoso_1

NetworkId           : 10.11.0.0/16

CustomConfiguration : ADSite=Contoso;
Name                : Contoso_2

NetworkId           : 10.12.0.0/16

CustomConfiguration : ADSite=Contoso;
```

This command gets all non-virtualized subnets assigned to the site named Contoso AD-Site.

### Example 3: Get all IPv4 subnets
```
PS C:\> Get-IpamSubnet -AddressFamily IPv4 -NetworkType Provider -AddressSpace "Default"

Name                 : Contoso_3

NetworkId            : 10.13.0.0/16

NetworkType          : Provider

Overlapping          : False

NetworkSite          :

VmmLogicalNetwork    :

ProviderAddressSpace : Default

CustomerAddressSpace :

VlanId               :

Owner                :
```

This command gets all provider IPv4 subnets in the default address space.

### Example 4: Get all unmapped non-virtualized subnets
```
PS C:\> Get-IpamSubnet -AddressFamily IPv4 -NetworkType NonVirtualized -Unmapped
Name                 : 10.0.0.0/24

NetworkId            : 10.0.0.0/24

NetworkType          : NonVirtualized

Overlapping          : False

NetworkSite          :

VmmLogicalNetwork    :

ProviderAddressSpace : Default

CustomerAddressSpace :

VlanId               :

Owner                :
Name                 : Contoso_1

NetworkId            : 10.10.1.0/24

NetworkType          : NonVirtualized

Overlapping          : True

NetworkSite          :

VmmLogicalNetwork    :

ProviderAddressSpace : Default

CustomerAddressSpace :

VlanId               :

Owner                :
```

This command gets all unmapped non-virtualized subnets in the default address space

### Example 5: Get all subnets in a customer address space
```
PS C:\> Get-IpamSubnet -AddressFamily IPv4 -NetworkType Customer -AddressSpace ContosoWest|Where {$_.VmmLogicalNetwork -eq "Storage"}
Name                 : ContosoWest_3

NetworkId            : 192.168.64.0/24

Type                 : Virtual

Overlapping          : False

NetworkSite          : Contoso

VmmLogicalNetwork    : Storage

ProviderAddressSpace : ContosoDatacenter

CustomerAddressSpace : ContosoWest

VlanId               :

Owner                :
Name                 : ContosoWest_4

NetworkId            : 20.22.16.0/24

Type                 : Virtual

Overlapping          : False

NetworkSite          : Contoso

VmmLogicalNetwork    : Storage

ProviderAddressSpace : ContosoDatacenter

CustomerAddressSpace : ContosoWest

VlanId               :

Owner                :
```

This command gets all subnets that belong to the ContosoWest customer address space and a logical network.

## PARAMETERS

### -AddressFamily
Specifies an address family of IP addresses.

The acceptable values for this parameter are:

- IPv4
- IPv6

```yaml
Type: AddressFamily[]
Parameter Sets: ByAF
Aliases:
Accepted values: IPv4, IPv6

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AddressSpace
Specifies an array of names of address spaces.
If you not specify an address space, the cmdlet gets data for all address spaces configured in IPAM.

```yaml
Type: String[]
Parameter Sets: ById, ByAF
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

### -MappingToBlock
Specifies the subnets that map to an address block.

```yaml
Type: CimInstance
Parameter Sets: ByBlock
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NetworkId
Specifies an array of networks and prefixes.
Specify the network ID in Classless Interdomain Routing (CIDR) notation in the format Network/Prefix.

```yaml
Type: String[]
Parameter Sets: ById
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkType
Specifies the type of network for the given subnet.

The acceptable values for this parameter are:

- Provider
 --  Customer
 --  NonVirtualized

If the value of the parameter is Default, then this parameter can take the value Provider or NonVirtualized.
If the value of the parameter is Provider, then the value of this parameter, if specified, must be Provider.
Specifying any other value for this parameter will result in an error.
Similarly, if the value of the parameter is Customer, then the value of this parameter, if specified, must be Customer.
Specifying any other value for this parameter will result in an error.

If you do not specify this parameter, the cmdlet returns all subnets that match the criteria, regardless of network type.

```yaml
Type: VirtualizationType[]
Parameter Sets: ById, ByAF
Aliases:
Accepted values: NonVirtualized, Provider, Customer

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Unmapped
Indicates that the cmdlet gets subnets that are not mapped to any IP address block.

```yaml
Type: SwitchParameter
Parameter Sets: ByAF
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### IpamSubnet

## NOTES

## RELATED LINKS

[Add-IpamSubnet](./Add-IpamSubnet.md)

[Export-IpamSubnet](./Export-IpamSubnet.md)

[Import-IpamSubnet](./Import-IpamSubnet.md)

[Remove-IpamSubnet](./Remove-IpamSubnet.md)

[Set-IpamSubnet](./Set-IpamSubnet.md)

