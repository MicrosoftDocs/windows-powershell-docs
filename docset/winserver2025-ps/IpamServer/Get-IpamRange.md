---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamRange.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/get-ipamrange?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IpamRange
---

# Get-IpamRange

## SYNOPSIS
Gets a set of IP address ranges from an IPAM server.

## SYNTAX

### ByID
```
Get-IpamRange -StartIPAddress <IPAddress[]> -EndIPAddress <IPAddress[]> [-ManagedByService <String[]>]
 [-ServiceInstance <String[]>] [-NetworkType <VirtualizationType[]>] [-AddressSpace <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByAF
```
Get-IpamRange -AddressFamily <AddressFamily[]> [-AddressCategory <AddressCategory[]>]
 [-ManagedByService <String[]>] [-ServiceInstance <String[]>] [-NetworkType <VirtualizationType[]>]
 [-AddressSpace <String[]>] [-Unmapped] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByBlock
```
Get-IpamRange -MappingToBlock <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### BySubnet
```
Get-IpamRange -MappingToSubnet <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamRange** cmdlet gets a set of IP address ranges from IP Address Management (IPAM).
Use this cmdlet to get IP address ranges of a particular address family or to get a particular range based on starting and ending IP addresses.
The cmdlet includes parameter sets to get all ranges that map to a given IP address block or a subnet.

## EXAMPLES

### Example 1: Get all IPv4 address ranges
```
PS C:\> Get-IpamRange -AddressFamily IPv4 -AddressCategory Private -AddressSpace "Default"
```

This command gets all private physical IPv4 address ranges, either provider or non virtualized.

### Example 2: Get all IPv4 ranges for a network type
```
PS C:\> Get-IpamRange -AddressFamily IPv4 -AddressCategory Private -NetworkType Provider
```

This command gets all private IPv4 ranges of network type provider that belong to any provider address space.

### Example 3: Get all IPv4 ranges in the default address space for a provider network type
```
PS C:\> Get-IpamRange -AddressFamily IPv4 -AddressCategory Private -NetworkType Provider -AddressSpace "Default"
```

This command gets all private IPv4 ranges of network type provider that belong to the default address space.

### Example 4: Get all IPv4 ranges for a customer network type
```
PS C:\> $PrivateCustomerRanges = Get-IpamRange -AddressFamily IPv4 -AddressCategory Private -NetworkType Customer
```

This command gets all private IPv4 ranges of network type customer, and stores the result in the variable named $PrivateCustomerRanges.

### Example 5: Get all IPv4 ranges for a network type and address space
```
PS C:\> $PrivateCustomerRanges = Get-IpamRange -AddressFamily IPv4 -AddressCategory Private -NetworkType Customer -AddressSpace Contoso
```

This command gets all private IPv4 addresses that are of network type Customer that belong to the Contoso customer address space.
The command stores the result in the variable named $PrivateCustomerRanges.

### Example 6: Get all IPv4 ranges between two addresses
```
PS C:\> $Range= Get-IpamRange -StartIPAddress 10.12.1.1 -EndIPAddress 10.12.1.254 -ManagedByService IPAM -ServiceInstance "localhost"
```

This command gets the details of a given IP address range, and stores the result in the variable named $Range.

### Example 7: Get all overlapping ranges
```
PS C:\> Get-IpamRange -AddressFamily IPv4 -AddressCategory Private -AddressSpace "Default" | where {$Overlapping -eq $True}
Overlapping      : True

NetworkID        : 172.16.19.0/24

StartAddress     : 172.16.19.10

EndAddress       : 172.16.19.110

ManagedByService : VMM

ServiceInstance  : vmm1.contoso.com

NetworkType      : Provider

Owner            :
Overlapping      : True

NetworkID        : 172.16.19.0/24

StartAddress     : 172.16.19.50

EndAddress       : 172.16.19.150

ManagedByService : IPAM

ServiceInstance  : Localhost

NetworkType      : NonVirtualized

Owner            :
```

This command gets all overlapping ranges from the default address space.
Both Provider and NonVirtualized ranges can exist in the default address space.
In IPAM, IP ranges are marked overlapping if they belong to same address space and their start and end IP addresses overlap.

### Example 8: Get all IPv4 ranges for a subnet
```
PS C:\> $ContosoPhysicalSubnet = Get-IpamSubnet -NetworkId 10.12.0.0/16
PS C:\> $AddressMappingToSubnet = Get-IpamRange -MappingToSubnet $ContosoPhysicalSubnet
```

This example gets all IP ranges which map to a given subnet.
Since the network type of the subnet here is non-virtualized, the results contain only the physical addresses and the fabric addresses from the default address space that maps to this subnet.

The first command uses the **Get-IpamSubnet** cmdlet to get a subnet, and stores the result in the variable named $ContosoPhysicalSubnet.

The second command gets the IP address ranges and stores the result in the $AddressMappingToSubnet variable.

## PARAMETERS

### -AddressCategory
Specifies an array of address families of IP addresses.
The acceptable values for this parameter are:

- IPv4
- IPv6

```yaml
Type: AddressCategory[]
Parameter Sets: ByAF
Aliases:
Accepted values: Public, Private, Global

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AddressFamily
Specifies an array of address families of IP address range objects that this cmdlet gets.
The acceptable values for this parameter are:

- IPv4
- IPv6

```yaml
Type: AddressFamily[]
Parameter Sets: ByAF
Aliases:
Accepted values: IPv4, IPv6

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AddressSpace
Specifies an array of address spaces of the IP address ranges to query.
If you do not specify a value, the cmdlet gets data for all address spaces in IPAM.

```yaml
Type: String[]
Parameter Sets: ByID, ByAF
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

### -EndIPAddress
Specifies an array of IP addresses.
For this parameter, the addresses represent the high end of the ranges to get.

```yaml
Type: IPAddress[]
Parameter Sets: ByID
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ManagedByService
Specifies an array of services that manage the range to get.

```yaml
Type: String[]
Parameter Sets: ByID, ByAF
Aliases: MB

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MappingToBlock
Specifies the ranges that map to an address block.

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

### -MappingToSubnet
Specifies an IP range that maps to a subnet.

```yaml
Type: CimInstance
Parameter Sets: BySubnet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NetworkType
Specifies an array of network types for the addresses that this cmdlet gets.

The acceptable values for this parameter are:

- Provider
 --  Customer
 --  NonVirtualized

If the value of the  parameter is Default, then this parameter can take the value Provider or NonVirtualized.
If the value of the parameter is Provider, then the value of this parameter, if specified, must be Provider.
Specifying any other value for this parameter will result in an error.
Similarly, if the value of the parameter is Customer, then the value of this parameter, if specified, must be Customer.
Specifying any other value for this parameter will result in an error.

If you specify the *NetworkType* parameter but do not specify the *AddressType* parameter, the cmdlet returns all IP address ranges of the given network type.

```yaml
Type: VirtualizationType[]
Parameter Sets: ByID, ByAF
Aliases:
Accepted values: NonVirtualized, Provider, Customer

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceInstance
Specifies an array of service instances that manage the address ranges to get.

```yaml
Type: String[]
Parameter Sets: ByID, ByAF
Aliases: SI

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartIPAddress
Specifies an array of IP addresses.
For this parameter, the addresses represent the high end of the ranges to get.

```yaml
Type: IPAddress[]
Parameter Sets: ByID
Aliases:

Required: True
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
Indicates that the cmdlet gets the unmapped ranges.

```yaml
Type: SwitchParameter
Parameter Sets: ByAF
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### CimInstance#ROOT/microsoft/ipam/MSFT_IPAM_Range
This cmdlet returns an array of IP address ranges that are present in IPAM datastore.

## NOTES

## RELATED LINKS

[Add-IpamRange](./Add-IpamRange.md)

[Export-IpamRange](./Export-IpamRange.md)

[Import-IpamRange](./Import-IpamRange.md)

[Remove-IpamRange](./Remove-IpamRange.md)

[Set-IpamRange](./Set-IpamRange.md)

[Get-IpamSubnet](./Get-IpamSubnet.md)

