---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetVirtualizationLookupRecordSettingData.cdxml-help.xml
Module Name: NetWNV
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netwnv/new-netvirtualizationlookuprecord?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetVirtualizationLookupRecord
---

# New-NetVirtualizationLookupRecord

## SYNOPSIS
Creates a policy entry for an IP address in a virtual network.

## SYNTAX

```
New-NetVirtualizationLookupRecord -CustomerAddress <String> -VirtualSubnetID <UInt32> -MACAddress <String>
 -ProviderAddress <String> [-CustomerID <String>] [-Context <String>] -Rule <RuleType> [-VMName <String>]
 [-UseVmMACAddress <Boolean>] [-Type <Type>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-NetVirtualizationLookupRecord** cmdlet creates a lookup record policy entry for an IP address that belongs to a Microsoft® Hyper-V® Server 2016 virtual network.
Network Virtualization allows for more than one virtual network to exist on the same physical network.
Computers can exchange network traffic with a virtual machine by using a Customer Address in the virtual network.
Network Virtualization manages the Provider Addresses that are the physical network addresses.
This cmdlet creates a record that maps a Customer Address to a Provider Address.
For more information, see [Network Virtualization technical details](https://technet.microsoft.com/library/jj134174.aspx) on TechNet.

To create a policy entry, you must specify a Customer Address, a virtual machine media access control (MAC) address, a Provider Address, a rule type, and a virtual subnet ID.
You can also specify a context, a customer ID, and a virtual machine name in addition to whether to use a virtual machine virtual MAC address.

## EXAMPLES

### Example 1: Create a policy entry
```
PS C:\> New-NetVirtualizationLookupRecord -CustomerAddress "10.0.0.5" -MACAddress "101010101105" -ProviderAddress "192.168.1.101" -Rule "TranslationMethodEncap" -VirtualSubnetID "6000" -VMName "BlueS1-VM1"
```

This command creates a policy entry for a Customer Address 10.0.0.5.
The command specifies the required values: a MAC address for the virtual machine, the physical Provider Address, a rule type, and a virtual subnet ID.
The rule type is TranslationMethodEncap, which means the entry uses NVGRE.
The command also specifies a name for the virtual machine.

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

### -Context
Specifies a comment regarding the policy entry.
Administrators can use this comment for any purpose.

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

### -CustomerAddress
Specifies the IP address for a virtual machine.
You can use can use either an IPv4 or IPv6 address.

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

### -CustomerID
Specifies an ID for a policy entry or virtual machine.
Administrators can use this setting for any purpose.

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

### -MACAddress
Specifies a MAC address that corresponds to the Customer Address.

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

### -ProviderAddress
Specifies an IP address, either IPv4 or IPv6, for a physical address that corresponds to the Customer Address.

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

### -Rule
Specifies which type of virtualization mechanism that the policy entry uses.
The acceptable values for this parameter are:

- TranslationMethodNat.
IP address rewrite.
- TranslationMethodEncap.
Network Virtualization Generic Routing Encapsulation (NVGRE).
- TranslationMethodNone.
None.

```yaml
Type: RuleType
Parameter Sets: (All)
Aliases: 
Accepted values: TranslationMethodNat, TranslationMethodEncap, TranslationMethodNone

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

### -Type
Specifies a type.
The type determines the address mapping for a record.
The acceptable values for this parameter are:

- Static.
The Customer Address (CA) specified in this lookup record is the address assigned to the corresponding virtual machine, which is implicitly specified by the MAC address.
An administrator or vmmblue_1 creates this lookup record. 
- Dynamic.
The Customer Address specified in this lookup record is the address assigned to the corresponding virtual machine, which is implicitly specified by the MAC address.
For example, the Hyper-V Network Virtualization software creates this record for virtual machines that obtain their IP addresses from a DHCP server. 
- L2Only.
The Customer Address specified in this lookup record should be set to 0.0.0.0 for IPv4, or :: for IPv6.
The corresponding virtual machine, implicitly specified by the MAC address, learns the CA dynamically. 
- GatewayWildcard.
The CA address specified in this lookup record should be set to 0.0.0.0 for IPv4, or :: for IPv6.
The corresponding virtual machine, implicitly specified by the MAC address, is a Hyper-V Network Virtualization gateway.

```yaml
Type: Type
Parameter Sets: (All)
Aliases: 
Accepted values: Static, Dynamic, GatewayWildcard, L2Only

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseVmMACAddress
Indicates whether this entry uses its defined MAC address instead of physical MAC address.
Virtual networking can use different MAC addresses for different virtual machines to balance traffic among multiple CPU cores.

A value of $True is valid only if the *Rule* parameter has a value of TranslationMethodNat.
The default value for this setting is $False.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMName
Specifies a name for the virtual machine for this policy entry.
Administrators can use this name for any purpose.

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

### -VirtualSubnetID
Specifies an ID for the virtual subnet that the Customer address belongs to.
The acceptable values for this parameter are: integers from 4096 through 16777214.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-NetVirtualizationLookupRecord](./Get-NetVirtualizationLookupRecord.md)

[Remove-NetVirtualizationLookupRecord](./Remove-NetVirtualizationLookupRecord.md)

[Set-NetVirtualizationLookupRecord](./Set-NetVirtualizationLookupRecord.md)

