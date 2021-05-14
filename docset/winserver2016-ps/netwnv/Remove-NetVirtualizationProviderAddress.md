---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetVirtualizationProviderAddressSettingData.cdxml-help.xml
Module Name: NetWNV
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/netwnv/remove-netvirtualizationprovideraddress?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-NetVirtualizationProviderAddress
---

# Remove-NetVirtualizationProviderAddress

## SYNOPSIS
Deletes Provider Addresses.

## SYNTAX

### ByName (Default)
```
Remove-NetVirtualizationProviderAddress [-ProviderAddress <String[]>] [-InterfaceIndex <UInt32[]>]
 [-PrefixLength <Byte[]>] [-VlanID <UInt16[]>] [-AddressState <AddressState[]>] [-MACAddress <String[]>]
 [-ManagedByCluster <Boolean[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Remove-NetVirtualizationProviderAddress -InputObject <CimInstance[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-NetVirtualizationProviderAddress** cmdlet deletes Provider Addresses configured in Microsoft® Hyper-V® Server 2016 Network Virtualization.
A Provider Address is an IPv4 or IPv6 address that Network Virtualization uses for multiple virtual Customer Addresses.
For more information, see [Network Virtualization technical details](https://technet.microsoft.com/library/jj134174.aspx) on TechNet.

You can specify which Provider Addresses to delete by using address state, interface index, prefix length, IP address, or VLAN ID, or you can use the Get-NetVirtualizationProviderAddress cmdlet to get Provider Addresses to delete.

You can use this cmdlet to remove a Provider Address when no virtual machines use that address.
If you deleted or migrated all the virtual machines from a Hyper-V Server 2016 host, you could then remove the Provider Address.

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

This command removes all the Provider Addresses on the interface that have an index of 13.

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
Parameter Sets: ByName
Aliases: 
Accepted values: Invalid, Tentative, Duplicate, Deprecated, Preferred

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -InputObject
Specifies the input object that is used in a pipeline command.

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

### -InterfaceIndex
Specifies an array of indexes for network interfaces that have Hyper-V Server 2016 Network Virtualization enabled.

```yaml
Type: UInt32[]
Parameter Sets: ByName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MACAddress
Specifies an array of media access control (MAC) addresses that corresponds to the Provider Address.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedByCluster
Specifies an array of Boolean values that determines whether a highly available Provider Address configuration entry exists on a Hyper-V Network Virtualization gateway.
If you use a Provider Address cluster resource, this value is $True.
Otherwise, the value is $False.
This parameter is a read-only parameter that is used by an administrator to diagnose problems.

```yaml
Type: Boolean[]
Parameter Sets: ByName
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
Parameter Sets: ByName
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
Parameter Sets: ByName
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

### -VlanID
Specifies an array of IDs for VLANs for Provider Addresses.

```yaml
Type: UInt16[]
Parameter Sets: ByName
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

[New-NetVirtualizationProviderAddress](./New-NetVirtualizationProviderAddress.md)

[Set-NetVirtualizationProviderAddress](./Set-NetVirtualizationProviderAddress.md)

