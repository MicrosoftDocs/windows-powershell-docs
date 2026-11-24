---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamAddress.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/add-ipamaddress?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-IpamAddress
---

# Add-IpamAddress

## SYNOPSIS
Adds an IP address to IPAM.

## SYNTAX

```
Add-IpamAddress [-IpAddress] <IPAddress> [[-ManagedByService] <String>] [[-ServiceInstance] <String>]
 [-NetworkType <VirtualizationType>] [-AddressSpace <String>] [-DeviceType <String>] [-IpAddressState <String>]
 [-AssignmentType <AddressAssignment>] [-MacAddress <String>] [-AssignmentDate <DateTime>]
 [-ExpiryDate <DateTime>] [-Description <String>] [-Owner <String>] [-AssetTag <String>]
 [-SerialNumber <String>] [-ClientId <String>] [-Duid <String>] [-Iaid <UInt32>] [-ReservationServer <String>]
 [-ReservationName <String>] [-ReservationType <DhcpReservationType>] [-ReservationDescription <String>]
 [-DeviceName <String>] [-ForwardLookupZone <String>] [-ForwardLookupPrimaryServer <String>]
 [-ReverseLookupZone <String>] [-ReverseLookupPrimaryServer <String>] [-CustomConfiguration <String>]
 [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-IpamAddress** cmdlet adds an IP address to IP Address Management (IPAM).
You can use the cmdlet to associate the Dynamic Host Configuration Protocol (DHCP) reservation properties with the IP address.
The cmdlet does not create a reservation on the DHCP server.
You can use Windows PowerShell for DHCP Server to create a reservation on the DHCP server.

## EXAMPLES

### Example 1: Add a physical IP address to the IPAM server
```
PS C:\> Add-IpamAddress -IpAddress 10.12.3.5 -PassThru
IpAddress        : 10.12.3.5

Type             : NonVirtualized

Duplicate        : False

ExpiryStatus     : Not Expired

MacAddress       :

ManagedByService : IPAM

ServiceInstance  : Localhost

DeviceName       :

DeviceType       : Host

IpAddressState   : In-Use

AssignmentType   : Static
```

This command adds the physical IP address 10.12.3.5 to the default address space that the current instance of the IPAM server manages.
The command uses the following default values for the address:

- *ManagedByService* parameter uses the default value IPAM
- *ServiceInstance* parameter uses the default value Localhost
- *DeviceType* parameter uses the default value Host
- *AssignmentType* parameter uses the default value Static

### Example 2: Assign a dynamic IP address to a virtual machine
```
PS C:\> Add-IpamAddress -IpAddress 10.12.4.9 -ManagedByService "TSQA DHCP" -ServiceInstance "dhcp1.contoso.com" -AssignmentType Dynamic -DeviceType VM -ExpiryDate $TwoWeeksFromNow -PassThru
IpAddress        : 10.12.4.9

Type             : NonVirtualized

Duplicate        : False

ExpiryStatus     : Not Expired

MacAddress       :

ManagedByService : MS DHCP

ServiceInstance  : dhcp1.contoso.com

DeviceName       :

DeviceType       : VM

IpAddressState   : In-Use

AssignmentType   : Dynamic
```

This command assigns the IP address 10.12.4.8 to a virtual machine.
The command specifies that the DHCP server named dhcp1.contoso.com manages the address.
The command specifies that the address expires in two weeks, at which time you can reclaim it.

### Example 3: Add a provider IP address to the IPAM server
```
PS C:\> Add-IpamAddress -NetworkType Provider -IpAddress 172.16.10.16 -PassThru
IpAddress         : 172.16.10.16

NetworkType       : Provider

Duplicate         : False

ExpiryStatus      : Not Expired

MacAddress        :

ManagedByService  : IPAM

ServiceInstance   : Localhost

DeviceName        :

DeviceType        : Host

IpAddressState    : In-Use

AssignmentType    : Static
```

This command adds the provider IP address 172.16.10.16 (which the current instance of IPAM manages) to the default address space.

### Example 4: Add a provider IP address that  Virtual Machine Manager manages
```
PS C:\> Add-IpamAddress -IpAddress 172.16.10.16 -AddressSpace "Datacenter01" -ManagedByService VMM -ServiceInstance "vmm1.contoso.com" -PassThru
IpAddress         : 172.16.10.16

NetworkType       : Provider

Duplicate         : False

ExpiryStatus      : Not Expired

MacAddress        :

ManagedByService  : VMM

ServiceInstance   : vmm1.contoso.com

DeviceName        :

DeviceType        : Host

IpAddressState    : In-Use

AssignmentType    : Static
```

This command adds a provider IP address that is managed by vmmblue_1 and belongs to the provider address space named Datacenter01.
vmmblue_2 statically manages the address assignment.
Because this address is in a different address space, IPAM does not mark it as a duplicate.

### Example 5: Add a customer IP address that a Virtual Machine Manager instance manages
```
PS C:\> Add-IpamAddress -IpAddress 172.16.10.16 -Virtual -AddressSpace "Datacenter01" -ManagedByService VMM -ServiceInstance "vmm01.contoso.com" -DeviceType VM
IpAddress         : 172.16.10.16

NetworkType       : Customer

Duplicate         : False

ExpiryStatus      : Not Expired

MacAddress        :

ManagedByService  : VMM

ServiceInstance   : vmm01.contoso.com

DeviceName        :

DeviceType        : VM

IpAddressState    : In-Use

AssignmentType    : Static
```

This command adds a customer IP address that the vmmblue_1 instance vmm01.contoso.com manages.
The address is added to the customer address space for the tenant named Datacenter01.

## PARAMETERS

### -AddressSpace
Specifies the address space that is associated with the IP address.
The default value is Default.

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
To obtain a **DateTime** object, use the **Get-Date** cmdlet.
For more information, type `Get-Help Get-Date`.

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
Specifies how IPAM assigns this address.
The acceptable values for this parameter are:

- Static
- Dynamic
- Auto
- VIP
- Reserved

The default value is Static.

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
Specifies the ID of the client.

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

### -CustomConfiguration
Specifies semicolon-separated name/value pairs.
This parameter specifies custom metadata that is associated with the address.

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
Specify a value that exists in the built-in **DeviceType** custom field.
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
Specifies the name of the DNS server that IPAM uses to resolve host names to IP addresses.

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
Specifies the name of the forward lookup zone that contains a mapping of host names to IP addresses.

```yaml
Type: String
Parameter Sets: (All)
Aliases: FwdLookupZone

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

### -IpAddress
Specifies an IP address that this cmdlet adds to IPAM.

```yaml
Type: IPAddress
Parameter Sets: (All)
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
Type: String
Parameter Sets: (All)
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

The default value is NonVirtualized.

If you specify Default for the **AddressSpace** parameter, the valid values for this parameter are Provider and NonVirtualized.
If you specify a provider type of address space for the **AddressSpace** parameter, you must specify Provider for this parameter.
If you specify a customer type of address space for the **AddressSpace** parameter, you must specify Customer for this parameter.

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
Specifies the name of the owner of the address.

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
Specifies the protocols that the reservation supports.
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
Specifies the reverse lookup zone that contains the mapping from IP addresses to fully qualified domain names (FQDNs).

```yaml
Type: String
Parameter Sets: (All)
Aliases: RevLookupZone

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SerialNumber
Specifies the serial number of the device that is associated with the IP address.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SN

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceInstance
Specifies the instance of the service that manages the IP address.
Specify the instance of the service that you specified for the *ManagedByService* parameter.
The value that you specify for this parameter must exist in the set of values that you defined for the **ServiceInstance** custom field in IPAM.

```yaml
Type: String
Parameter Sets: (All)
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
Represents an IP address on the IPAM server.

## NOTES

## RELATED LINKS

[Get-IpamAddress](./Get-IpamAddress.md)

[Set-IpamAddress](./Set-IpamAddress.md)

[Remove-IpamAddress](./Remove-IpamAddress.md)

[Import-IpamAddress](./Import-IpamAddress.md)

[Export-IpamAddress](./Export-IpamAddress.md)

[Get-IpamCustomField](./Get-IpamCustomField.md)

[Get-IpamAddressSpace](./Get-IpamAddressSpace.md)

