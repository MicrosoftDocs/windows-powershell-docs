---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetVirtualizationProviderAddressSettingData.cdxml-help.xml
Module Name: NetWNV
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/netwnv/set-netvirtualizationprovideraddress?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetVirtualizationProviderAddress
---

# Set-NetVirtualizationProviderAddress

## SYNOPSIS
Changes a VLAN ID or prefix length for a Provider Address.

## SYNTAX

### ByName (Default)
```
Set-NetVirtualizationProviderAddress [-ProviderAddress <String[]>] [-InterfaceIndex <UInt32[]>]
 [-AddressState <AddressState[]>] [-VlanID <UInt16>] [-PrefixLength <Byte>] [-MACAddress <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetVirtualizationProviderAddress -InputObject <CimInstance[]> [-VlanID <UInt16>] [-PrefixLength <Byte>]
 [-MACAddress <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetVirtualizationProviderAddress** cmdlet changes a virtual local area network (VLAN) ID or prefix length for Provider Addresses used with Microsoft® Hyper-V® Server 2016 Network Virtualization.
For more information, see [Network Virtualization technical details](https://technet.microsoft.com/library/jj134174.aspx) on TechNet.

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

This command uses the Get-NetVirtualizationProviderAddress cmdlet to get all the Provider Addresses for the interface that has the index 23, and then passes them to the Set-NetVirtualizationProviderAddress cmdlet by using the pipeline operator.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-NetVirtualizationProviderAddress](./Get-NetVirtualizationProviderAddress.md)

[New-NetVirtualizationProviderAddress](./New-NetVirtualizationProviderAddress.md)

[Remove-NetVirtualizationProviderAddress](./Remove-NetVirtualizationProviderAddress.md)

