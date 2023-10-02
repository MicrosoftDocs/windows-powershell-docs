---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetVirtualizationProviderAddressSettingData.cdxml-help.xml
Module Name: NetWNV
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netwnv/new-netvirtualizationprovideraddress?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetVirtualizationProviderAddress
---

# New-NetVirtualizationProviderAddress

## SYNOPSIS
Assigns a Provider Address to a network interface.

## SYNTAX

```
New-NetVirtualizationProviderAddress -ProviderAddress <String> -InterfaceIndex <UInt32> -PrefixLength <Byte>
 [-VlanID <UInt16>] [-MACAddress <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-NetVirtualizationProviderAddress** cmdlet assigns a Provider Address to a network interface for use with Microsoft® Hyper-V® Server 2016 Network Virtualization.
A Provider Address is an IPv4 or IPv6 address that Network Virtualization uses for multiple virtual Customer Addresses.
For more information, see [Network Virtualization technical details](https://technet.microsoft.com/library/jj134174.aspx) on TechNet.

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
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -InterfaceIndex
Specifies the index for a network interface that has Hyper-V Server 2016 Network Virtualization enabled.

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

### -MACAddress
Specifies a media access control (MAC) address that corresponds to the Provider Address.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-NetVirtualizationProviderAddress](./Get-NetVirtualizationProviderAddress.md)

[Remove-NetVirtualizationProviderAddress](./Remove-NetVirtualizationProviderAddress.md)

[Set-NetVirtualizationProviderAddress](./Set-NetVirtualizationProviderAddress.md)

