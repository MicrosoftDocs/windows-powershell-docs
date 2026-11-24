---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamAddress.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/get-ipamaddress?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IpamAddress
---

# Get-IpamAddress

## SYNOPSIS
Gets IP addresses from IPAM.

## SYNTAX

### ByAddress
```
Get-IpamAddress [-IpAddress] <IPAddress[]> [-ManagedByService <String[]>] [-ServiceInstance <String[]>]
 [-NetworkType <VirtualizationType[]>] [-AddressSpace <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByAddressFamily
```
Get-IpamAddress -AddressFamily <AddressFamily[]> [-AddressCategory <AddressCategory[]>]
 [-ManagedByService <String[]>] [-ServiceInstance <String[]>] [-NetworkType <VirtualizationType[]>]
 [-AddressSpace <String[]>] [-Unmapped] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByBlock
```
Get-IpamAddress -MappingToBlock <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### BySubnet
```
Get-IpamAddress -MappingToSubnet <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByRange
```
Get-IpamAddress -MappingToRange <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamAddress** cmdlet gets IP addresses from IP Address Management (IPAM).
Specify the *IpAddress* parameter to retrieve an IP address.
Specify the *AddressFamily* parameter to retrieve a set of IP addresses for address families.
You can also get addresses that belong to a range, a subnet, or an address block.

## EXAMPLES

### Example 1: Get all private physical IPv4 addresses
```
PS C:\> Get-IpamAddress -AddressFamily IPv4 -AddressCategory Private -AddressSpace "Default"
```

This command gets all private physical IPv4 addresses in IPAM.
Because the command specifies the Default address space, the command gets provider or non-virtualized IP addresses from all address spaces in IPAM.

### Example 2: Get private IPv4 addresses for provider networks
```
PS C:\> Get-IpamAddress -AddressFamily IPv4 -AddressCategory Private -NetworkType Provider
```

This command gets all private IPv4 addresses for provider networks.
Because the command does not specify the *AddressSpace* parameter, the command gets addresses that belong to all address spaces in IPAM.

### Example 3: Get private IPv4 addresses from the default address space
```
PS C:\> Get-IpamAddress -AddressFamily IPv4 -AddressCategory Private -NetworkType Provider -AddressSpace "Default"
```

This command gets all private IPv4 addresses for provider networks.
Because the command specifies the Default address space, the command gets IP addresses from all address spaces configured in IPAM.

### Example 4: Get private IPv4 addresses for customer networks
```
PS C:\> Get-IpamAddress -AddressFamily IPv4 -AddressCategory Private -NetworkType Customer
```

This command gets all private IPv4 addresses for customer networks.
Because the command does not specify the *AddressSpace* parameter, the command gets addresses that belong to all address spaces configured in IPAM.

### Example 5: Get private IPv4 addresses for customer networks from an address space
```
PS C:\> Get-IpamAddress -AddressFamily IPv4 -AddressCategory Private -NetworkType Customer -AddressSpace "ContosoAddSpace01"
```

This command gets all private IPv4 addresses for customer networks that belong to the address space named ContosoAddSpace01.

### Example 6: Get physical IP addresses from all address spaces
```
PS C:\> Get-IpamAddress -IpAddress 10.12.1.1, 10.12.3.1
```

This command gets the physical IP addresses 10.12.1.1 and 10.12.3.1.
Because the command does not specify the *AddressSpace* parameter, the command gets IP addresses from all address spaces which match the IP address 10.12.1.1 and 10.12.3.1.

### Example 7: Get duplicate addresses in an address space
```
PS C:\> Get-IpamAddress -AddressFamily IPv4 -AddressSpace Default | Where-Object {$_.duplicate -eq $true} | Format-List IPAddress, NetworkType, ManagedByService, ServiceInstance, ProviderAddressSpace
IpAddress            : 172.16.10.16

NetworkType          : Provider

ManagedByService     : VMM

ServiceInstance      : vmm1.contoso.com

ProviderAddressSpace : Default
IpAddress            : 172.16.10.16

NetworkType          : Provider

Duplicate            : True

ManagedByService     : IPAM

ServiceInstance      : Localhost

ProviderAddressSpace : Default
```

This command gets all duplicate IPv4 addresses in the default provider address space.
The Default address space is the address space to which the IPAM entity belongs.
The command returns two addresses that have the IP address 172.16.10.16.
One address is managed by IPAM and the other address is managed by vmmblue_1.
The IPAM server marks both these addresses as duplicate.
The command uses the **Format-List** cmdlet to display the output in the form of a table.
For more information, type `Get-Help Format-Table`.

### Example 8: Get IP addresses that map to a subnet
```
PS C:\> $ContosoPhysicalSubnet = Get-IpamSubnet -NetworkId "10.12.0.0/16"
PS C:\> Get-IpamAddress -MappingToSubnet $ContosoPhysicalSubnet
```

This example gets all IP addresses that map to a subnet.
Because the network type of the subnet is non-virtualized, the result contains only physical addresses and the fabric addresses from the default address space which belong to the subnet.

The first command uses the **Get-IpamSubnet** cmdlet to get the **IpamSubnet** object that contain subnets configured in IPAM for the network that has the ID 10.12.0.0/16.
The command stores the object in the **$ContosoPhysicalSubnet** variable.

The second command gets all the IP addresses that belong to the IP subnet stored in the **$ContosoPhysicalSubnet** variable.

### Example 9: Get all IP address that map to a an IP range
```
PS C:\> $Range = Get-IpamRange -StartIPAddress 10.12.1.1 -EndIPAddress 10.12.1.254
PS C:\> Get-IpamAddress -MappingToRange $Range
```

This example gets all IP addresses that belong to a range of IP addresses.

The first command uses the **Get-IpamRange** cmdlet to get an **IpamRange** object that contains an IP range configured in IPAM.
The command stores the object in the $Range variable.

The second command gets all the IP addresses that belong to the range stored in the $Range variable.

## PARAMETERS

### -AddressCategory
Specifies an array of IP address categories.
If you specify this parameter, you must specify the *AddressFamily*  parameter.

The acceptable values for this parameter are:
- Public
- Private

```yaml
Type: AddressCategory[]
Parameter Sets: ByAddressFamily
Aliases:
Accepted values: Public, Private, Global

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AddressFamily
Specifies an array of address families of IP addresses.

The acceptable values for this parameter are:

- IPv4
- IPv6

```yaml
Type: AddressFamily[]
Parameter Sets: ByAddressFamily
Aliases:
Accepted values: IPv4, IPv6

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AddressSpace
Specifies an array of names of address spaces.
If you do not specify this parameter, the cmdlet gets the addresses for all address spaces in IPAM.
If you specify this parameter, you must specify the *AddressFamily* parameter.

```yaml
Type: String[]
Parameter Sets: ByAddress, ByAddressFamily
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

### -IpAddress
Specifies an array of IP addresses.

```yaml
Type: IPAddress[]
Parameter Sets: ByAddress
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ManagedByService
Specifies an array of names of the services that manage the IP addresses.
The values that you specify for this parameter must exist in the set of values that you defined for the **ManagedByService** custom field in IPAM.

You can use the Add-IpamCustomValue to add a value to the **ManagedByService** custom field in IPAM.
You can use the Remove-IpamCustomValue to remove a value from the **ManagedByService** custom field in IPAM.

```yaml
Type: String[]
Parameter Sets: ByAddress, ByAddressFamily
Aliases: MB

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MappingToBlock
Specifies an IP block.
The cmdlet gets the addresses that belong to the IP block.

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

### -MappingToRange
Specifies an IP address range.
The cmdlet gets the addresses that belong to the IP range.

```yaml
Type: CimInstance
Parameter Sets: ByRange
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MappingToSubnet
Specifies an IP subnet.
The cmdlet gets the addresses that belong to the IP subnet.

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
Specifies the network type of the address.
The acceptable values for this parameter are:

- Provider
- Customer
- NonVirtualized

The default value is NonVirtualized.

If you specify Default for the *AddressSpace* parameter, the valid values for this parameter are Provider and NonVirtualized.
If you specify a provider type of address space for the *AddressSpace* parameter, you must specify Provider for this parameter.
If you specify a customer type of address space for the *AddressSpace* parameter, you must specify Customer for this parameter.

```yaml
Type: VirtualizationType[]
Parameter Sets: ByAddress, ByAddressFamily
Aliases:
Accepted values: NonVirtualized, Provider, Customer

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceInstance
Specifies an array of instances of the services that manage the IP addresses.
Specify the instances of the service that you specified for the *ManagedByService* parameter.
The value that you specify for this parameter must exist in the set of values that you defined for the **ServiceInstance** custom field in IPAM.

```yaml
Type: String[]
Parameter Sets: ByAddress, ByAddressFamily
Aliases: SI

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
Indicates that the cmdlet gets addresses that do not belong to any address families of IP addresses in IPAM.

```yaml
Type: SwitchParameter
Parameter Sets: ByAddressFamily
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

### IpamAddress[]
This cmdlet returns an object that represents a set of IP addresses on the IPAM server.

## NOTES

## RELATED LINKS

[Set-IpamAddress](./Set-IpamAddress.md)

[Add-IpamAddress](./Add-IpamAddress.md)

[Remove-IpamAddress](./Remove-IpamAddress.md)

[Import-IpamAddress](./Import-IpamAddress.md)

[Export-IpamAddress](./Export-IpamAddress.md)

[Add-IpamCustomValue](./Add-IpamCustomValue.md)

[Remove-IpamCustomValue](./Remove-IpamCustomValue.md)

[Get-IpamSubnet](./Get-IpamSubnet.md)

[Get-IpamRange](./Get-IpamRange.md)

