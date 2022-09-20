---
external help file: NetWNV_Cmdlets.xml
Module Name: NetWNV
online version: https://learn.microsoft.com/powershell/module/netwnv/set-netvirtualizationprovideraddress?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NetVirtualizationProviderAddress

## SYNOPSIS
Changes a VLAN ID or prefix length for a Provider Address.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NetVirtualizationProviderAddress [-AddressState <AddressState[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-InterfaceIndex <UInt32[]>] [-PassThru] [-PrefixLength <Byte>] [-ProviderAddress <String[]>]
 [-ThrottleLimit <Int32>] [-VlanID <UInt16>]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NetVirtualizationProviderAddress [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-PrefixLength <Byte>]
 [-ThrottleLimit <Int32>] [-VlanID <UInt16>] -InputObject <CimInstance[]>
```

## DESCRIPTION
The **Set-NetVirtualizationProviderAddress** cmdlet changes a virtual local area network (VLAN) ID or prefix length for Provider Addresses used with hv_win8_1 Network Virtualization.
For more information, see Network Virtualization technical detailshttp://technet.microsoft.com/library/jj134174.aspx (http://technet.microsoft.com/library/jj134174.aspx) on TechNet.

You can specify which Provider Addresses to modify by using address state, interface index, or IP address, or you can use the Get-NetVirtualizationProviderAddress cmdlet to get Provider Addresses to modify.

## EXAMPLES

### Example 1: Change a virtual LAN ID
```
PS C:\> Set-NetVirtualizationProviderAddress -ProviderAddress "192.168.2.3" -InterfaceIndex 17 -VlanID 201
```

This command changes the virtual LAN ID for the Provider Address 192.168.2.3 on the interface that has the Index 17.

### Example 2: Change a virtual LAN ID for specified Provider Addresses
```
PS C:\>Get-NetVirtualizationProviderAddress -InterfaceIndex 23 | Set-NetVirtualizationProviderAddress -VlanID 20
```

This command uses the Get-NetVirtualizationProviderAddress cmdlet to get all the Provider Addresses for the interface that has the index 23, and then passes them to the Set-NetVirtualizationProviderAddress cmdlet by using the pipe operator.
The command assigns a value of 20 for the virtual LAN ID of all the Provider Address for the interface.

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
Accept wildcard characters: True
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
Specifies the length of an IP prefix.

```yaml
Type: Byte
Parameter Sets: (All)
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
Specifies an ID for a VLAN for the Provider Address.

```yaml
Type: UInt16
Parameter Sets: (All)
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

[Remove-NetVirtualizationProviderAddress](./Remove-NetVirtualizationProviderAddress.md)

