---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamRange.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/set-ipamrange?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-IpamRange
---

# Set-IpamRange

## SYNOPSIS
Modifies an existing IP address range.

## SYNTAX

### Query (cdxml) (Default)
```
Set-IpamRange [-StartIPAddress] <IPAddress[]> [-EndIPAddress] <IPAddress[]> [-ManagedByService <String[]>]
 [-ServiceInstance <String[]>] [-NetworkType <VirtualizationType[]>] [-AddressSpace <String[]>]
 [-CreateSubnetIfNotFound] [-NewNetworkId <String>] [-NewStartIPAddress <IPAddress>]
 [-NewEndIPAddress <IPAddress>] [-NewManagedByService <String>] [-NewServiceInstance <String>]
 [-NewNetworkType <VirtualizationType>] [-NewAddressSpace <String>] [-AssignmentType <AddressAssignment>]
 [-AssignmentDate <DateTime>] [-UtilizationCalculation <UtilizationCalculation>] [-UtilizedAddresses <Double>]
 [-Description <String>] [-Owner <String>] [-ReservedAddress <String[]>] [-DnsServer <IPAddress[]>]
 [-DnsSuffix <String[]>] [-ConnectionSpecificDnsSuffix <String>] [-WinsServer <IPAddress[]>] [-VIP <String[]>]
 [-Gateway <String[]>] [-AddCustomConfiguration <String>] [-RemoveCustomConfiguration <String>]
 [-AssociatedReverseLookupZone <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-IpamRange -InputObject <CimInstance[]> [-CreateSubnetIfNotFound] [-NewNetworkId <String>]
 [-NewStartIPAddress <IPAddress>] [-NewEndIPAddress <IPAddress>] [-NewManagedByService <String>]
 [-NewServiceInstance <String>] [-NewNetworkType <VirtualizationType>] [-NewAddressSpace <String>]
 [-AssignmentType <AddressAssignment>] [-AssignmentDate <DateTime>]
 [-UtilizationCalculation <UtilizationCalculation>] [-UtilizedAddresses <Double>] [-Description <String>]
 [-Owner <String>] [-ReservedAddress <String[]>] [-DnsServer <IPAddress[]>] [-DnsSuffix <String[]>]
 [-ConnectionSpecificDnsSuffix <String>] [-WinsServer <IPAddress[]>] [-VIP <String[]>] [-Gateway <String[]>]
 [-AddCustomConfiguration <String>] [-RemoveCustomConfiguration <String>]
 [-AssociatedReverseLookupZone <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-IpamRange** cmdlet modifies an existing IP address range that an IP Address Management (IPAM) server manages.

## EXAMPLES

### Example 1: Modify an existing IP address range
```
PS C:\> Get-IpamRange -StartIPAddress 10.12.1.1 -EndIPAddress 10.12.1.254|Set-IpamRange -NewManagedByService VMM -NewServiceInstance "vmm1.contoso.com" -PassThru

Overlapping      : False

NetworkID        : 10.12.0.0/16

StartAddress     : 10.12.1.1

EndAddress       : 10.12.1.254

ManagedByService : VMM

ServiceInstance  : vmm1.contoso.com

NetworkType      : NonVirtualized

Owner            :
```

This command modifies an existing IP address range that is currently managed by IPAM, to be managed by Virtual Machine Manager (VMM).

The command includes the *PassThru* parameter, so it displays results to the console.

### Example 2: Add custom metadata to an IP address range
```
PS C:\> Get-IpamRange -StartIPAddress 10.12.1.1 -EndIPAddress 10.12.1.254|Set-IpamRange -AddCustomConfiguration "ADSite=ContosoCorporate" -PassThru| Format-List Overlapping, StartAddress, EndAddress, ManagedByService, ServiceInstance, CustomConfiguration

Overlapping         : False

StartAddress        : 10.12.1.1

EndAddress          : 10.12.1.254

ManagedByService    : VMM

ServiceInstance     : vmm1.contoso.com

CustomConfiguration : ADSite= ContosoCorporate;
```

This command adds custom metadata to an IP range by using a custom field to identify the location.

The command includes the *PassThru* parameter, so it displays results to the console.

### Example 3: Modify the network type for an IP address range
```
PS C:\> Set-IpamRange -StartIPAddress 10.12.3.1 -EndIPAddress 10.12.3.254 -ManagedByService IPAM -ServiceInstance localhost -AddressSpace "Default" -NetworkType NonVirtualized -NewNetworkType Provider -PassThru

Overlapping      : False

NetworkID        : 10.12.0.0/16

StartAddress     : 10.12.3.1

EndAddress       : 10.12.3.254

ManagedByService : IPAM

ServiceInstance  : Localhost

NetworkType      : Provider

Owner            :
```

This command modifies the network type of an IP address range from non-virtualized to provider.
By default, the provider address range will be assigned to the default provider address space.

The command includes the *PassThru* parameter, so it displays results to the console.

### Example 4: Modify the network type for an IP address range to its previous state
```
PS C:\> Set-IpamRange -StartIPAddress 10.12.3.1 -EndIPAddress 10.12.3.254 -ManagedByService IPAM -ServiceInstance localhost -AddressSpace Default -NetworkType Provider -NewNetworkType NonVirtualized -PassThru

Overlapping      : False

NetworkID        : 10.12.0.0/16

StartAddress     : 10.12.3.1

EndAddress       : 10.12.3.254

ManagedByService : IPAM

ServiceInstance  : Localhost

NetworkType      : NonVirtualized

Owner            :
```

This command modifies the network type of an IP address range from provider to non-virtualized.
The non-virtualized address range will be added to the default address space.
You cannot specify the provider address space in this case.

The command includes the *PassThru* parameter, so it displays results to the console.

### Example 5: Modify the network type for an IP address range and assign the IP addresses
```
PS C:\> Set-IpamRange -StartIPAddress 10.12.3.1 -EndIPAddress 10.12.3.254 -ManagedByService IPAM -ServiceInstance localhost -AddressSpace Default -NetworkType NonVirtualized -NewNetworkType Provider -NewAddressSpace ContosoDataCenter -PassThru | Format-List IpAddress, NetworkType, ProviderAddressSpace, CustomerAddressSpace
Overlapping       : False

NetworkID         : 10.12.0.0/16

StartAddress      : 10.12.3.1

EndAddress        : 10.12.3.254

ManagedByService  : IPAM

ServiceInstance   : Localhost

NetworkType       : Provider

ProviderAddressSpace : ContosoDataCenter

CustomerAddressSpace :
```

This command modifies the network type of an IP address from non-virtualized to provider.
The command assigns the IP address to the provider address space ContosoDataCenter.

The command includes the *PassThru* parameter, so it displays results to the console.

## PARAMETERS

### -AddCustomConfiguration
Specifies semi-colon (;) separated name/value pairs.
This parameter specifies custom metadata that are associated with the address space.

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

### -AddressSpace
Specifies an array of names of address spaces.
If you do not specify a value, the cmdlet modifies matching ranges from all address spaces.

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
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

### -AssignmentDate
Specifies the date on which to assign addresses in this range.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AssignmentType
Specifies the address assignment type from this range.

The acceptable values for this parameter are:

- Static
- Dynamic
- Auto
- VIP
- Reserved

```yaml
Type: AddressAssignment
Parameter Sets: (All)
Aliases:
Accepted values: Static, Dynamic, Auto, VIP, Reserved

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AssociatedReverseLookupZone


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

### -ConnectionSpecificDnsSuffix
Specifies the connection-specific DNS suffix to associate with this range.

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

### -CreateSubnetIfNotFound
Indicates that the cmdlet creates a parent subnet for this range of addresses.
If you specify this parameter, the cmdlet automatically creates a parent subnet for this range, if no parent subnet exists.

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

### -Description
Specifies a description for the range to modify.

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

### -DnsServer
Specifies an array of Domain Name System (DNS) servers to associate with this range.
Specify the names of the DNS servers in the order of preference, highest to lowest.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DnsSuffix
Specifies an array of suffixes.

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

### -EndIPAddress
Specifies an array of IP addresses.
For this parameter, the addresses represent the high end of the range to modify.

```yaml
Type: IPAddress[]
Parameter Sets: Query (cdxml)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Gateway
Specifies an array of gateway servers, imported from a Dynamic Host Configuration Protocol (DHCP) scope, to associate with a range in IPAM.
Specify the names of the gateway servers in the order of preference, highest to lowest.
The format for specification is \<ipaddress\>\\\<metric\>.
To specify Automatic metric, the format is \<Ipaddress\>\Automatic.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

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

### -ManagedByService
Specifies an array of services that manage the range to modify.

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
Aliases: MB

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkType
Specifies an array of network types for the addresses to modify.

The acceptable values for this parameter are:

- Provider
- Customer
- NonVirtualized

If you do not specify a value, the cmdlet modifies all matching IP address ranges of network type Provider, Customer, and NonVirtualized.

```yaml
Type: VirtualizationType[]
Parameter Sets: Query (cdxml)
Aliases:
Accepted values: NonVirtualized, Provider, Customer

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewAddressSpace
Specifies the name of a new address space for the IP address range.
A range with network type NonVirtualized can only belong to Default address space.
A range with network type Provider can belong to either the Default address space or a Provider address space.
A range with network type Customer can only belong to a Customer address space.

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

### -NewEndIPAddress
Specifies a new IP address.
For this parameter, the address represents the new high end of the range.
An error occurs if the value is not compatible with the network ID and the starting IP address.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewManagedByService
Specifies the name of a new value of the **ManagedByService** property.

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

### -NewNetworkId
Specifies the name of a new value of the **NetworkId** property.
Choose a value compatible with the existing beginning and ending IP addresses for the range, or specify new values for starting and ending IP addresses.

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

### -NewNetworkType
Specifies the name of a new value of network type for this address.
You can change the network type from NonVirtualized to Provider, or from Provider to NonVirtualized.
However, you cannot convert network type from NonVirtualized or Provider to Customer.

```yaml
Type: VirtualizationType
Parameter Sets: (All)
Aliases:
Accepted values: NonVirtualized, Provider

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewServiceInstance
Specifies the name of a new value of the service instance property.
Choose a new value compatible with the value of *ManagedByService* parameter.

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

### -NewStartIPAddress
Specifies a new IP address.
For this parameter, the address represents the new low end of the range.
An error occurs if the value is not compatible with the network ID and the ending IP address.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Owner
Specifies the name of an owner for an address range.

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

### -RemoveCustomConfiguration
Specifies a list of custom metadata fields to remove from the range object.
The list is a string of name-value pairs, separated by semicolons (;).

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

### -ReservedAddress
Specifies an array of reserved addresses from the given range.
This list will overwrite the existing list of reserved addresses for the given range.

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

### -ServiceInstance
Specifies an array of service instances that manage the address ranges to modify.

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
Aliases: SI

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartIPAddress
Specifies an array of IP addresses.
For this parameter, the addresses represent the low end of the range to modify.

```yaml
Type: IPAddress[]
Parameter Sets: Query (cdxml)
Aliases:

Required: True
Position: 1
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

### -UtilizationCalculation
Specifies whether the utilization information will be automatically calculated by IPAM or specified by the user.
The utilization calculation provides a visual alert when the utilization level of IP addresses is greater than a threshold value.

```yaml
Type: UtilizationCalculation
Parameter Sets: (All)
Aliases:
Accepted values: Auto, UserSpecified

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UtilizedAddresses
Specifies the number of addresses to utilize from the pool of IP addresses.
Use this parameter when the utilization calculation is set to the value in **UserSpecified**.

```yaml
Type: Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VIP
Specifies an array of virtual IP addresses, usually set aside for load balancers, from the range.
Specify the Virtual IPs (VIP) as a list, in descending order of precedence.
This list overwrites any existing VIPs specified for the given range.

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

### -WinsServer
Specifies an array of Windows Internet Name Service (WINS) servers to associate with this range.
Specify the WINS servers in decreasing order of precedence.
This list overwrites any existing list of WINS servers.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
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

### CimInstance#ROOT/microsoft/ipam/MSFT_IPAM_Range
This cmdlet returns an object that contains the modified IP address range.

## NOTES

## RELATED LINKS

[Add-IpamRange](./Add-IpamRange.md)

[Export-IpamRange](./Export-IpamRange.md)

[Get-IpamRange](./Get-IpamRange.md)

[Import-IpamRange](./Import-IpamRange.md)

[Remove-IpamRange](./Remove-IpamRange.md)

