---
external help file: NetWNV_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 70B81AF5-345B-4140-B820-ACF8A5A31F2D
manager: dansimp
---

# New-NetVirtualizationProviderAddress

## SYNOPSIS
Assigns a Provider Address to a network interface.

## SYNTAX

```
New-NetVirtualizationProviderAddress [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-VlanID <UInt16>] -InterfaceIndex <UInt32> -PrefixLength <Byte> -ProviderAddress <String>
```

## DESCRIPTION
The **New-NetVirtualizationProviderAddress** cmdlet assigns a Provider Address to a network interface for use with hv_win8_1 Network Virtualization.
A Provider Address is an IPv4 or IPv6 address that Network Virtualization uses for multiple virtual Customer Addresses.
For more information, see Network Virtualization technical detailshttp://technet.microsoft.com/library/jj134174.aspx (http://technet.microsoft.com/library/jj134174.aspx) on TechNet.

To assign a Provider Address, specify the IP address, an interface, and the IP prefix length for the subnet.
You can also specify a virtual local area network (VLAN) ID.

## EXAMPLES

### Example 1: Assign an IPv4 Provider Address
```
PS C:\> New-NetVirtualizationProviderAddress -InterfaceIndex 13 -PrefixLength 24 -ProviderAddress "10.0.1.23" -VlanID 103
```

This command assigns a Provider Address to a network interface that has an index of 13.
The address is 10.0.1.23, with a prefix length of 24.
The command also specifies a virtual LAN ID.

### Example 2: Assign an IPv6 Provider Address
```
PS C:\>New-NetVirtualizationProviderAddress -InterfaceIndex 12 -PrefixLength 48 -ProviderAddress "2001:DB8:11:22:33:44:55:6"
```

This command assigns a Provider Address to a network interface that has an index of 12.
The address is an IPv6 address, with a prefix length of 48.

## PARAMETERS

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

### -InterfaceIndex
Specifies the index for a network interface that has hv_win8_2 Network Virtualization enabled.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrefixLength
Specifies the length of the IP prefix.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderAddress
Specifies an IP address configured for the network interface.
You can use IPv4 or IPv6 addresses.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

### -VlanID
Specifies an ID for a LAN for the Provider Address.

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

[Remove-NetVirtualizationProviderAddress](./Remove-NetVirtualizationProviderAddress.md)

[Set-NetVirtualizationProviderAddress](./Set-NetVirtualizationProviderAddress.md)

