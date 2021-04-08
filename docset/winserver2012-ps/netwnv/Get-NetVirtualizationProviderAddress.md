---
author: Kateyanne
external help file: NetWNV_Cmdlets.xml
manager: dansimp
Module Name: NetWNV
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/netwnv/get-netvirtualizationprovideraddress?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetVirtualizationProviderAddress

## SYNOPSIS
Gets Provider Addresses.

## SYNTAX

```
Get-NetVirtualizationProviderAddress [-AddressState <AddressState[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-InterfaceIndex <UInt32[]>] [-PrefixLength <Byte[]>] [-ProviderAddress <String[]>] [-ThrottleLimit <Int32>]
 [-VlanID <UInt16[]>]
```

## DESCRIPTION
The **Get-NetVirtualizationProviderAddress** cmdlet gets Provider Addresses configured in hv_win8_1 Network Virtualization.
A Provider Address is an IPv4 or IPv6 address that Network Virtualization uses for multiple virtual Customer Addresses.
For more information, see Network Virtualization technical detailshttp://technet.microsoft.com/library/jj134174.aspx (http://technet.microsoft.com/library/jj134174.aspx) on TechNet.

You can specify which Provider Addresses to get by using address state, interface index, prefix length, IP address, or VLAN ID.
You can use this cmdlet to get Provider Addresses for other cmdlets, such as the Set-NetVirtualizationProviderAddress cmdlet or the Remove-NetVirtualizationProviderAddress cmdlet.

## EXAMPLES

### Example 1: Get Provider Addresses for an interface
```
PS C:\> Get-NetVirtualizationProviderAddress -InterfaceIndex 13
```

This command gets the Provider Address for the interface with the specified index.

### Example 2: Get a specific Provider Address
```
PS C:\>Get-NetVirtualizationProviderAddress -ProviderAddress "172.16.2.3"
```

This command gets the Provider Address that has the IP address 172.16.2.3.

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
Parameter Sets: (All)
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
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -InterfaceIndex
Specifies an array of indexes for network interfaces that have hv_win8_2 Network Virtualization enabled.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -PrefixLength
Specifies an array of lengths of IP prefixes.

```yaml
Type: Byte[]
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
You can use IPv4 and IPv6 addresses.

```yaml
Type: String[]
Parameter Sets: (All)
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

[New-NetVirtualizationProviderAddress](./New-NetVirtualizationProviderAddress.md)

[Remove-NetVirtualizationProviderAddress](./Remove-NetVirtualizationProviderAddress.md)

[Set-NetVirtualizationProviderAddress](./Set-NetVirtualizationProviderAddress.md)

