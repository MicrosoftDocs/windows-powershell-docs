---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamAddress.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/set-ipamaddress?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-IpamAddress
---

# Set-IpamAddress

## SYNOPSIS
Modifies an IP address in IPAM.

## SYNTAX

### ByAddress
```
Set-IpamAddress [-IpAddress] <IPAddress[]> [[-ManagedByService] <String[]>] [[-ServiceInstance] <String[]>]
 [-NetworkType <VirtualizationType[]>] [-AddressSpace <String[]>] [-NewIPAddress <IPAddress>]
 [-NewManagedByService <String>] [-NewServiceInstance <String>] [-NewNetworkType <VirtualizationType>]
 [-NewAddressSpace <String>] [-DeviceType <String>] [-IpAddressState <String>]
 [-AssignmentType <AddressAssignment>] [-AssignmentDate <DateTime>] [-MacAddress <String>]
 [-ExpiryDate <DateTime>] [-Description <String>] [-Owner <String>] [-AssetTag <String>]
 [-SerialNumber <String>] [-ClientId <String>] [-Duid <String>] [-Iaid <UInt32>] [-ReservationServer <String>]
 [-ReservationName <String>] [-ReservationType <DhcpReservationType>] [-ReservationDescription <String>]
 [-DeviceName <String>] [-ForwardLookupZone <String>] [-ForwardLookupPrimaryServer <String>]
 [-ReverseLookupZone <String>] [-ReverseLookupPrimaryServer <String>] [-AddCustomConfiguration <String>]
 [-RemoveCustomConfiguration <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-IpamAddress -InputObject <CimInstance[]> [-NewIPAddress <IPAddress>] [-NewManagedByService <String>]
 [-NewServiceInstance <String>] [-NewNetworkType <VirtualizationType>] [-NewAddressSpace <String>]
 [-DeviceType <String>] [-IpAddressState <String>] [-AssignmentType <AddressAssignment>]
 [-AssignmentDate <DateTime>] [-MacAddress <String>] [-ExpiryDate <DateTime>] [-Description <String>]
 [-Owner <String>] [-AssetTag <String>] [-SerialNumber <String>] [-ClientId <String>] [-Duid <String>]
 [-Iaid <UInt32>] [-ReservationServer <String>] [-ReservationName <String>]
 [-ReservationType <DhcpReservationType>] [-ReservationDescription <String>] [-DeviceName <String>]
 [-ForwardLookupZone <String>] [-ForwardLookupPrimaryServer <String>] [-ReverseLookupZone <String>]
 [-ReverseLookupPrimaryServer <String>] [-AddCustomConfiguration <String>]
 [-RemoveCustomConfiguration <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-IpamAddress** cmdlet modifies an IP address in IP Address Management (IPAM).
Specify the IP addresses to modify or use the *InputObject* parameter to specify an *IpamAddress* object to modify.

You can use the cmdlet to associate the Dynamic Host Configuration Protocol (DHCP) reservation properties with the IP address.
The cmdlet does not create a reservation on the DHCP server.
You can use Windows PowerShell for DHCP Server to create a reservation on the DHCP server.

## EXAMPLES

### Example 1: Reassign an IP address
```
PS C:\> Get-IpamAddress -IpAddress 172.16.10.10 | Set-IpamAddress -NewManagedByService "VMM" -NewServiceInstance "vmm1.contoso.com" -DeviceType "VM" -PassThru
IpAddress        : 172.16.10.10

NetworkType      : NonVirtualized

Duplicate        : False

ExpiryStatus     : Static

MacAddress       :

ManagedByService : VMM

ServiceInstance  : vmm1.contoso.com

DeviceName       :

DeviceType       : VM

IpAddressState   : In-Use

AssignmentType   : Static
```

This command gets an **IpamAddress** object that contains the IP address 172.16.10.10 that is managed by IPAM.
The command passes the **IpamAddress** object to the **Set-IpamAddress** cmdlet by using the pipeline operator.
The **Set-IpamAddress** cmdlet changes the service that manages the IP address to VMM, and changes the instance of the service that manages the IP address to vmm1.contoso.com.
The command assigns the address to the virtual machine device type.

### Example 2: Add custom metadata to an IP address
```
PS C:\> Get-IpamAddress -IpAddress 172.16.10.10 | Set-IpamAddress -AddCustomConfiguration "ADSite=Main"
```

This command adds custom metadata to the IP address 172.16.10.10.
The command adds the value Main to the custom field named ADSite.

### Example 3: Convert the network type of an IP address from non-virtualized to provider
```
PS C:\> Set-IpamAddress -IpAddress 172.16.10.10 -AddressSpace "Default" -NetworkType NonVirtualized -NewNetworkType Provider


IpAddress        : 172.16.10.10

NetworkType      : Provider

Duplicate        : False

ExpiryStatus     : Static

MacAddress       :

ManagedByService : VMM

ServiceInstance  : vmm1.contoso.com

DeviceName       :

DeviceType       : Host

IpAddressState   : In-Use

AssignmentType   : Static
```

This command converts the network type of the IP address 172.16.10.10 from non-virtualized to provider.
The command assigns the provider address to the default provider address space.

### Example 4: Convert the network type of an IP address from provider to non-virtualized
```
PS C:\> Set-IpamAddress -IpAddress 172.16.10.10 -NetworkType Provider -NewNetworkType NonVirtualized -PassThru | Format-List IpAddress, NetworkType, ProviderAddressSpace, CustomerAddressSpace
IpAddress            : 172.16.10.10

NetworkType          : NonVirtualized

ProviderAddressSpace : Default

CustomerAddressSpace :
```

This command converts the network type of the IP address 172.16.10.10 from provider to non-virtualized.
By default, the command assigns the non-virtualized address to the Default address space.
The command passes the output to the **Format-List** cmdlet by using the pipeline operator, and formats the output as a table.
For more information, type `Get-Help Format-List`.

### Example 5: Assign an IP address to a new address space
```
PS C:\> Set-IpamAddress -IpAddress 172.16.10.10 -NetworkType NonVirtualized -NewNetworkType Provider -NewAddressSpace MainDataCenter -PassThru | Format-List IpAddress, NetworkType, ProviderAddressSpace, CustomerAddressSpace
IpAddress            : 172.16.10.10

NetworkType          : Provider

ProviderAddressSpace : MainDataCenter

CustomerAddressSpace :
```

This command converts the network type of the IP address 172.16.10.10 from non-virtualized to provider.
The command assigns the IP address to the provider address space named MainDataCenter.
The command passes the output to the **Format-List** cmdlet by using the pipeline operator, and formats the output as a table.

## PARAMETERS

### -AddCustomConfiguration
Specifies semi-colon (;) separated name and value pairs of custom metadata.
The cmdlet adds the custom configuration metadata to the IP addresses.

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
Specifies the address space that is associated with the IP address.
The default value is Default.

```yaml
Type: String[]
Parameter Sets: ByAddress
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

### -AssetTag
Specifies the asset tag associated with the IP address.

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

### -AssignmentDate
Specifies the date on which you assigned the IP address to a device.

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
The default value is Static.

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

### -ClientId
Specifies the ID of the IPAM client.

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

### -Description
Specifies a description of the IP address assignment for a device.

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

### -DeviceName
Specifies the name of the device to which you assigned the address.

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

### -DeviceType
Specifies the type of device to which you assigned the address.
Specify a value that exists in the built-in custom field **DeviceType**.

The acceptable values for this parameter are:

- VM
- Host

The default value is Host.

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

### -Duid
Specifies the DHCP device unique identifier (DUID) for the client.
Clients use the DUID to get an IP address from a DHCPv6 server.

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

### -ExpiryDate
Specifies an expiry date for the address.
IPAM alerts the administrator when the IP address expires.
IPAM does not reclaim expired addresses automatically.

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

### -ForwardLookupPrimaryServer
Specifies the name of the Domain Name System (DNS) server that IPAM uses to resolve host names to IP addresses.

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

### -ForwardLookupZone
Specifies the name of the forward look up zone that contains mapping of host names to IP addresses.

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

### -Iaid
Specifies the identity association ID (IAID) of an IPv6 address.

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

### -IpAddressState
Specifies the usage state of the IP address.
By default, the cmdlet sets the address as In-Use.

You can specify a valid custom value for this parameter.
Use the **Add-IpamCustomValue** cmdlet to add a custom value to a custom field in IPAM.

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

### -MacAddress
Specifies the media access control (MAC) address of the device to which the address is assigned.

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

### -ManagedByService
Specifies the name of the service that manages the IP address.
The value that you specify for this parameter must exist in the set of values that you defined for the **ManagedByService** custom field in IPAM.

You can use the **Add-IpamCustomValue** cmdlet to add a value to the **ManagedByService** custom field in IPAM.
You can use the **Remove-IpamCustomValue** cmdlet to remove a value from the **ManagedByService** custom field in IPAM.

```yaml
Type: String[]
Parameter Sets: ByAddress
Aliases: MB

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkType
Specifies the network type of the address.

The acceptable values for this parameter are:

- Provider
- Customer
- NonVirtualized

The default value is NonVirtualized.If you specify Default for the *AddressSpace* parameter, the valid values for this parameter are Provider and NonVirtualized.
If you specify a provider type of address space for the *AddressSpace* parameter, you must specify Provider for this parameter.
If you specify a customer type of address space for the *AddressSpace* parameter, you must specify Customer for this parameter.

```yaml
Type: VirtualizationType[]
Parameter Sets: ByAddress
Aliases:
Accepted values: NonVirtualized, Provider, Customer

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewAddressSpace
Specifies the name of the new address space for the IP addresses.

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

### -NewIPAddress
Specifies an IP address.
The cmdlet assigns the new IP address to the IP addresses.

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
Specifies a new value for the service that manages the IP addresses.
The value that you specify for this parameter must exist in the set of values that you defined for the **ManagedByService** custom field in IPAM.

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
Specifies a new value for network type for the IP addresses.
You can change the network type from NonVirtualized to Provider, and from Provider to NonVirtualized.
You cannot be change the network type from NonVirtualized or Provider to Customer.

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
Specifies a new value for the instance of the service that manages the IP addresses.
The value that you specify for this parameter must exist in the set of values that you defined for the **ServiceInstance** custom field in IPAM.

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

### -Owner
Specifies the name of the owner of the IP addresses.

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
Specifies a semi-colon (;) separated string of custom field names.
The cmdlet removes the custom field names from the IP addresses.

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

### -ReservationDescription
Specifies a description for the DHCP reservation.

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

### -ReservationName
Specifies the name of the reservation on the DHCP server for the device.
You must specify a value for this parameter if you specify the *ReservationServer* parameter.

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

### -ReservationServer
Specifies the DHCP server on which the reservation is assigned.
The cmdlet stores the reservation data in IPAM.
The cmdlet does not create a reservation on the DHCP server.

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

### -ReservationType
Specifies the protocols supported by the reservation.
You must specify a value for this parameter if you specify the *ReservationServer* parameter.

The acceptable values for this parameter are:

- DHCP
- BootPr
- DHCP and BootPr

```yaml
Type: DhcpReservationType
Parameter Sets: (All)
Aliases:
Accepted values: None, Dhcp, Bootp, Both

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReverseLookupPrimaryServer
Specifies the DNS server that IPAM uses to resolve IP addresses to host names.

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

### -ReverseLookupZone
Specifies the reverse lookup zone that contains mapping from IP addresses to fully qualified domain names (FQDN).

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

### -SerialNumber
Specifies the serial number of the device to which you assigned the address.

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

### -ServiceInstance
Specifies an array of instances of the services that manage the IP addresses.
Specify the instances of the services that you specified for the *ManagedByService* parameter.
If you specify this parameter, you must specify the *IpAddress* parameter.
The value that you specify for this parameter must exist in the set of values that you defined for the *ServiceInstance* parameter.

```yaml
Type: String[]
Parameter Sets: ByAddress
Aliases: SI

Required: False
Position: 3
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

### IpamAddress
This cmdlet returns an object that represents an IP Address on the IPAM server.

## NOTES

## RELATED LINKS

[Get-IpamAddress](./Get-IpamAddress.md)

[Add-IpamAddress](./Add-IpamAddress.md)

[Remove-IpamAddress](./Remove-IpamAddress.md)

[Import-IpamAddress](./Import-IpamAddress.md)

[Export-IpamAddress](./Export-IpamAddress.md)

