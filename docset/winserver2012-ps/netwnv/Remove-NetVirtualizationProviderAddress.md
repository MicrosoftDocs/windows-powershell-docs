---
external help file: NetWNV_Cmdlets.xml
Module Name: NetWNV
online version: https://learn.microsoft.com/powershell/module/netwnv/remove-netvirtualizationprovideraddress?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-NetVirtualizationProviderAddress

## SYNOPSIS
Deletes Provider Addresses.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-NetVirtualizationProviderAddress [-AddressState <AddressState[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-InterfaceIndex <UInt32[]>] [-PassThru] [-PrefixLength <Byte[]>] [-ProviderAddress <String[]>]
 [-ThrottleLimit <Int32>] [-VlanID <UInt16[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-NetVirtualizationProviderAddress [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]>
```

## DESCRIPTION
The **Remove-NetVirtualizationProviderAddress** cmdlet deletes Provider Addresses configured in hv_win8_1 Network Virtualization.
A Provider Address is an IPv4 or IPv6 address that Network Virtualization uses for multiple virtual Customer Addresses.
For more information, see Network Virtualization technical detailshttp://technet.microsoft.com/library/jj134174.aspx (http://technet.microsoft.com/library/jj134174.aspx) on TechNet.

You can specify which Provider Addresses to delete by using address state, interface index, prefix length, IP address, or VLAN ID, or you can use the Get-NetVirtualizationProviderAddress cmdlet to get Provider Addresses to delete.

You can use this cmdlet to remove a Provider Address when no virtual machines (VMs) use that address.
If you deleted or migrated all the VMs from a hv_win8_2 host, you could then remove the Provider Address.

## EXAMPLES

### Example 1: Remove a Provider Address
```
PS C:\> Remove-NetVirtualizationProviderAddress -ProviderAddress "2001:DB8:11:22:33:44:55:6"
```

This command deletes the Provider Address 2001:DB8:11:22:33:44:55:6 on the current host.

### Example 2: Remove Provider Addresses for an interface
```
PS C:\>Remove-NetVirtualizationProviderAddress -InterfaceIndex 13
```

This command removes all the Provider Addresses on the interface that has an index of 13.

## PARAMETERS

### -AddressState
Specifies an array of states of Provider Addresses.
The acceptable values for this parameter are:

- Preferred.
The address is unique. 
- Tentative.
The address is not yet verified. 
- Duplicate.
There is a duplicate address on the network. 
- Invalid.
The address lifetime has expired. 
- Deprecated.
The address cannot start new connections.

```yaml
Type: AddressState[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
ps_cimcommon_asjob

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies an array of indexes for network interfaces that have hv_win8_2 Network Virtualization enabled.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -PrefixLength
Specifies an array of lengths of IP prefixes.

```yaml
Type: Byte[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderAddress
Specifies an array of IP addresses.
You can use IPv4 or IPv6 addresses.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
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

### -VlanID
Specifies an array of IDs for VLANs for Provider Addresses.

```yaml
Type: UInt16[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-NetVirtualizationProviderAddress](./Get-NetVirtualizationProviderAddress.md)

[New-NetVirtualizationProviderAddress](./New-NetVirtualizationProviderAddress.md)

[Set-NetVirtualizationProviderAddress](./Set-NetVirtualizationProviderAddress.md)

