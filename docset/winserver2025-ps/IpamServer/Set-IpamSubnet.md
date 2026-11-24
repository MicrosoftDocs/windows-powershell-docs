---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamSubnet.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/set-ipamsubnet?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-IpamSubnet
---

# Set-IpamSubnet

## SYNOPSIS
Modifies an existing IP subnet in IPAM.

## SYNTAX

### Query (cdxml) (Default)
```
Set-IpamSubnet -NetworkId <String[]> [-NetworkType <VirtualizationType[]>] [-AddressSpace <String[]>]
 [-NewNetworkId <String>] [-NewNetworkType <VirtualizationType>] [-NewAddressSpace <String>] [-Name <String>]
 [-Owner <String>] [-Description <String>] [-VlanId <UInt16[]>] [-VmmLogicalNetwork <String>]
 [-NetworkSite <String>] [-VirtualSubnetId <Int32>] [-AddCustomConfiguration <String>]
 [-RemoveCustomConfiguration <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-IpamSubnet -InputObject <CimInstance[]> [-NewNetworkId <String>] [-NewNetworkType <VirtualizationType>]
 [-NewAddressSpace <String>] [-Name <String>] [-Owner <String>] [-Description <String>] [-VlanId <UInt16[]>]
 [-VmmLogicalNetwork <String>] [-NetworkSite <String>] [-VirtualSubnetId <Int32>]
 [-AddCustomConfiguration <String>] [-RemoveCustomConfiguration <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-IpamSubnet** cmdlet modifies an existing IP subnet in IP Address Management (IPAM).

## EXAMPLES

### Example 1 Add metadata to a subnet
```
PS C:\> Get-IpamSubnet -AddressFamily IPv4|where {$_.Name -Like "Site*"}|Set-IpamSubnet -AddCustomConfiguration "ADSite=Site01" -PassThru | Format-List Name, NetworkId, CustomConfiguration

Name                : Site01_1

NetworkId           : 20.20.128.0/24

CustomConfiguration : ADSite=Site01; Name                : Site01_2

NetworkId           : 10.20.1.0/24

CustomConfiguration : ADSite=Site01;
Name                : Site01_3

NetworkId           : 10.20.2.0/24

CustomConfiguration : ADSite=Site01;
Name                : Site01_4

NetworkId           : 10.20.4.0/24

CustomConfiguration : ADSite=Site01;
Name                : Site01_5

NetworkId           : 10.20.8.0/24

CustomConfiguration : ADSite=Site01;
```

This command adds ADSite information as metadata to all subnets allocated to Site01.

The command includes the *PassThru* parameter, so it displays results to the console.

### Example 2: Modify a network ID
```
PS C:\> Set-IpamSubnet -NetworkId 10.10.1.0/16 -NetworkType NonVirtualized -NewNetworkId 10.10.1.0/17
```

This command modifies the NonVirtualized network ID of a subnet.

### Example 3: Rename a subnet
```
PS C:\> Set-IpamSubnet -NetworkId 10.10.1.0/17 -Name "Site01_2"
```

This command renames a subnet to Site01_2.

### Example 4: Convert the network type to provider
```
PS C:\> Set-IpamSubnet -NetworkId 10.10.1.0/17 -NetworkType NonVirtualized -NewNetworkType Provider
```

This command converts the network type of a subnet from NonVirtualized to Provider.
By default, the provider subnet will be assigned to default provider address space.

### Example 5: Convert the network type to non-virtualized
```
PS C:\> Set-IpamSubnet -NetworkId 10.10.1.0/17 -NetworkType Provider -NewNetworkType NonVirtualized
```

This command converts the network type of a subnet from Provider to NonVirtualized.

### Example 6: Convert the network type and assign to a provider address space
```
PS C:\> Set-IpamSubnet -NetworkId 10.10.1.0/17 -NetworkType NonVirtualized -NewNetworkType Provider -NewAddressSpace ContosoDataCenter
```

This command modifies the network type of a subnet from NonVirtualized to Provider, and assigns this subnet to the provider address space ContosoDataCenter.

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
Specifies an array of address spaces to which this IP address range belongs.
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

### -Description
Specifies a description for the subnet.

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

### -Name
Specifies the name for the subnet.

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

### -NetworkId
Specifies the network and the prefix for the given subnet.
Specify the network ID in Classless Interdomain Routing (CIDR) notation in the format Network/Prefix.

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkSite
Specifies a network site.
A network site is associated with a logical network and forms an abstraction of the physical network.
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
Specifies an array of network types for the subnets to modify.

The acceptable values for this parameter are:

- Provider
 --  Customer
 --  NonVirtualized

  If you do not specify a value, all matching IP subnets of network type Provider, Customer, and NonVirtualized will be modified.

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
Specifies the name of a new address space for the IP subnet.
A subnet of network type NonVirtualized can only belong to the Default address space.
A subnet of network type Provider can belong to either the Default address space or a Provider address space.
A subnet of network type Customer can only belong to a Customer address space.

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
Specifies the name of a new value of network ID for this subnet.

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

### -Owner
Specifies an owner for the subnet.

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
Specifies a list of custom metadata fields to modify.
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

```yaml
Type: Int32
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

### IpamSubnet
This cmdlet returns an object that represents a subnet in IPAM Server.

## NOTES
* When converting the network type of a subnet from Provider to NonVirtualized, the address space of  the subnet is reset to Default.

## RELATED LINKS

[Add-IpamSubnet](./Add-IpamSubnet.md)

[Export-IpamSubnet](./Export-IpamSubnet.md)

[Get-IpamSubnet](./Get-IpamSubnet.md)

[Import-IpamSubnet](./Import-IpamSubnet.md)

[Remove-IpamSubnet](./Remove-IpamSubnet.md)

