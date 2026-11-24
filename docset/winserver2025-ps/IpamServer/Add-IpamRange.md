---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamRange.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/add-ipamrange?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-IpamRange
---

# Add-IpamRange

## SYNOPSIS
Adds an IP address range to the configuration of an IPAM server.

## SYNTAX

```
Add-IpamRange [-CreateSubnetIfNotFound] [-NetworkId] <String> [[-StartIPAddress] <IPAddress>]
 [[-EndIPAddress] <IPAddress>] [-ManagedByService <String>] [-ServiceInstance <String>]
 [-NetworkType <VirtualizationType>] [-AddressSpace <String>]
 [-UtilizationCalculation <UtilizationCalculation>] [-UtilizedAddresses <Double>] [-Description <String>]
 [-Owner <String>] [-AssignmentType <AddressAssignment>] [-AssignmentDate <DateTime>]
 [-ReservedAddress <String[]>] [-DnsServer <IPAddress[]>] [-DnsSuffix <String[]>]
 [-ConnectionSpecificDnsSuffix <String>] [-WinsServer <IPAddress[]>] [-VIP <String[]>] [-Gateway <String[]>]
 [-CustomConfiguration <String>] [-AssociatedReverseLookupZone <String>] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-IpamRange** cmdlet adds an IP address range to the configuration of an IP Address Management (IPAM) server.
Use this cmdlet to add a Non-Virtualized, Provider, or a Customer IP address range in IPAM.
If the network type is Provider or NonVirtualized, the range will be added to default address space if you do not specify an address space.
If the network type is Customer, you must specify an address space.

## EXAMPLES

### Example 1: Add an IP address range
```
PS C:\> Add-IpamRange -NetworkId "10.13.0.0/16" -PassThru
Overlapping      : False

NetworkID        : 10.13.0.0/16

StartAddress     : 10.13.0.1

EndAddress       : 10.13.255.254

ManagedByService : IPAM

ServiceInstance  : Localhost

NetworkType      : NonVirtualized

Owner            :
```

This command adds an IP address range that is managed by the current instance of IPAM server.
This range is added to the default address space.

The command includes the *PassThru* parameter, so it displays results to the console.

### Example 2: Add an IP address range by using a network ID
```
PS C:\> Add-IpamRange -NetworkId "172.16.10.0/24"
Add-IpamRange : No subnet exists corresponding to the range.

At line:1 char:1

+ Add-IpamRange -NetworkId 172.16.10.0/24

+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

+ CategoryInfo          : ResourceUnavailable: (MSFT_IPAM_Range:ROOT/microsoft/ipam/MSFT_IPAM_Range) [Add-IpamRang

e], CimException

+ FullyQualifiedErrorId : WIN32 8,Add-IpamRange
```

This command adds an IP address range with network id 172.16.10.0/24.
IPAM does not allow creation of a range for which a corresponding subnet does not exist.

### Example 3: Add an IP address range by using a network ID and create a subnet
```
PS C:\> Add-IpamRange -NetworkId "172.16.10.0/24" -CreateSubnetIfNotFound -WinsServer "10.10.1.1","10.10.1.2" -Gateway "10.10.5.1/Automatic","10.10.5.2/4"|Format-List Overlapping, NetworkID, StartAddress, EndAddress, ManagedByService, ServiceInstance, WinsServers, Gateway
Overlapping      : False

NetworkID        : 172.16.10.0/24

StartAddress     : 172.16.10.1

EndAddress       : 172.16.10.254

ManagedByService : IPAM

ServiceInstance  : Localhost

WinsServers      : {10.10.1.1, 10.10.1.2}

Gateway          : {10.10.5.1/Automatic, 10.10.5.2/4}
```

This command adds an IP address range with network id 172.16.10.0/24.
The command uses the *CreateSubnetIfNotFound* parameter to automatically create the corresponding subnet, and adds WINS and Gateway servers to the range.
Gateway servers are specified in the format \<IP Address\>/\<Metric\>.

### Example 4: Add a provider IP address range to an existing IPAM configuration
```
PS C:\> Add-IpamRange -NetworkId 172.16.19.0/24 -StartIPAddress 172.16.19.10 -EndIPAddress 172.16.19.110 -NetworkType Provider -CreateSubnetIfNotFound -PassThru
Overlapping      : False

NetworkID        : 172.16.19.0/24

StartAddress     : 172.16.19.10

EndAddress       : 172.16.19.110

ManagedByService : IPAM

ServiceInstance  : Localhost

NetworkType      : Provider

Owner            :
```

This command adds a provider IP address range that is managed by current instance of IPAM.
The range will be added to default address space.

The command includes the *PassThru* parameter, so it displays results to the console.

### Example 5: Add a range of provider IP addresses
```
PS C:\> Add-IpamRange -NetworkId 172.16.19.0/24 -StartIPAddress 172.16.19.10 -EndIPAddress 172.16.19.110 -NetworkType Provider -AddressSpace ContosoDataCenter -PassThru -CreateSubnetIfNotFound
Overlapping      : False

NetworkID        : 172.16.19.0/24

StartAddress     : 172.16.19.10

EndAddress       : 172.16.19.110

ManagedByService : IPAM

ServiceInstance  : Localhost

NetworkType      : Provider

Owner            :
```

This command adds a provider IP range 172.16.19.0/24 with start and end IP addresses 172.16.19.10 and 172.16.19.110.
The command adds the range to a provider address space named ContosoDataCenter.
Since this range is in a different address space, IPAM will not mark it as overlapping.

The command includes the *PassThru* parameter, so it displays results to the console.

## PARAMETERS

### -AddressSpace
Specifies an address space to which this IP address range belongs.
An address space contains IP subnets, IP ranges, and IP addresses.
If you do not specify this parameter, the default address space is used.
The default address space is the Provider address space.

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

### -AssignmentDate
Specifies a date on which to assign addresses in this range.

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
Specifies how IPAM assigns the addresses.
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
Specifies a description for the range.

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
Specifies an array of DNS servers to associate with this range.
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
Specifies an array of search suffixes to associate with the given range.

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
Specifies an IP address.
For this parameter, the address represents the high end of the range to add.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Gateway
Specifies an array of gateway servers, imported from a DHCP Scope, to associate with a range in IPAM.
Specify the names of the gateway servers in the order of preference, highest to lowest.
The format for specification is \<ipaddress\>\\\<metric\>.
To specify the Automatic metric, use the format \<Ipaddress\>\Automatic.

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

### -ManagedByService
Specifies the value of the managing service of the IP address ranges being added.

```yaml
Type: String
Parameter Sets: (All)
Aliases: MB

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkId
Specifies the network and the prefix for the given range.
Specify the network ID in Classless Interdomain Routing (CIDR) notation in the format Network/Prefix.

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

### -NetworkType
Specifies an array of network types for the addresses to be added.
The acceptable values for this parameter are:

- Provider
- Customer
- NonVirtualized

 If the value of the *AddressSpace* parameter is Default, then this parameter can use the value Provider or NonVirtualized.
If the value of the *AddressSpace* parameter is Provider, then the value of this parameter, if specified, must be Provider.
Specifying any other value for this parameter will result in an error.
Similarly, if the value of the *AddressSpace* parameter is Customer, then the value of this parameter, if specified, must be Customer.
Specifying any other value for this parameter will result in an error.

If you do not specify this parameter, network type defaults to NonVirtualized.

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

### -ReservedAddress
Specifies the reserved addresses in the range.
Specify the reserved addresses as a list, in descending order of precedence.

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
Specifies the service instance that manages the address ranges to add.
The value specified for this field should be present in the set of values defined for the ServiceInstance custom field in IPAM.
The cmdlet will report an error if this is not found to be a valid value for the ServiceInstance custom field.
The user can edit the associated custom field to add or delete values.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SI

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartIPAddress
Specifies an IP address.
For this parameter, the address represents the low end of the range to add.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
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
Specifies the utilization information type that will be automatically calculated by IPAM or specified by the user.

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
Specifies an array of virtual IP addresses that are usually set aside for load balancers.
Specify the VIPs as a list, in descending order of precedence.

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
This cmdlet returns the IP address range object added to the IPAM data store.

## NOTES

## RELATED LINKS

[Export-IpamRange](./Export-IpamRange.md)

[Get-IpamRange](./Get-IpamRange.md)

[Import-IpamRange](./Import-IpamRange.md)

[Remove-IpamRange](./Remove-IpamRange.md)

[Set-IpamRange](./Set-IpamRange.md)

